---
title: 안전한 링크
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 이 문서에서 관리자는 피싱 및 악의적인 URL을 사용하는 기타 공격으로부터 조직을 보호하기 위해 Office 365용 Defender의 안전 링크 보호에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 251b3e71be30f90ac828abc8bf34877d65615336
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175778"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95b17-103">Office 365용 Microsoft Defender의 안전한 링크</span><span class="sxs-lookup"><span data-stu-id="95b17-103">Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95b17-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="95b17-104">**Applies to**</span></span>
- [<span data-ttu-id="95b17-105">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="95b17-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="95b17-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95b17-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="95b17-107">이 문서는 [Office 365용 Microsoft Defender](office-365-atp.md)가 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="95b17-108">Outlook.com, Microsoft 365 Family 또는 Microsoft 365 Personal을 사용 중일 때 Outlook의 Safelinks에 대한 자세한 내용은 고급 보안 Outlook.com [참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="95b17-108">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="95b17-109">안전한 링크는 [Office 365용 Defender의](office-365-atp.md) 기능으로, 메일 흐름에서 인바운드 전자 메일 메시지의 URL 검색 및 다시 기록, 클릭 시 전자 메일 메시지 및 기타 위치의 URL 및 링크 확인을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-109">Safe Links is a feature in [Defender for Office 365](office-365-atp.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="95b17-110">EOP(Exchange Online Protection)의 인바운드 전자 메일 메시지에서 일반 스팸 방지 및 맬웨어 방지 보호 기능 외에 안전한 링크 검색이 실행됩니다. [](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="95b17-110">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="95b17-111">안전한 링크 검색은 피싱 및 기타 공격에 사용되는 악의적인 링크로부터 조직을 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-111">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="95b17-112">안전한 링크 보호는 다음 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-112">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="95b17-113">**전자 메일 메시지:** 전자 메일 메시지의 링크에 대한 안전한 링크 보호는 안전한 링크 정책에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-113">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="95b17-114">기본 안전 링크 정책은 없습니다. 따라서 전자 메일 메시지의 안전한 링크 보호를 위해 하나 이상의 안전한 링크 정책을 **만들어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="95b17-114">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="95b17-115">자세한 내용은 [Office 365용 Microsoft Defender에서 안전한](set-up-atp-safe-links-policies.md)링크 정책 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-115">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

  <span data-ttu-id="95b17-116">전자 메일 메시지의 안전한 링크 보호에 [](#safe-links-settings-for-email-messages) 대한 자세한 내용은 이 문서 부분의 전자 메일 메시지에 대한 안전 링크 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-116">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="95b17-117">**Microsoft Teams(현재** TAP 미리 보기에서): Teams 대화, 그룹 채팅 또는 채널의 링크에 대한 안전한 링크 보호도 안전한 링크 정책에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-117">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="95b17-118">기본 안전 링크 정책은 없습니다. 따라서 Teams에서 안전한 링크 보호를 위해 하나 이상의 안전한 링크 정책을 **만들어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="95b17-118">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="95b17-119">Teams의 안전한 링크 보호에 대한 자세한 내용은 이 문서 부분의 [Microsoft Teams에](#safe-links-settings-for-microsoft-teams) 대한 안전 링크 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-119">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this article.</span></span>

- <span data-ttu-id="95b17-120">**Office 365 앱:** Office 365 앱에 대한 안전한 링크 보호는 지원되는 데스크톱, 모바일 및 웹 aps에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-120">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="95b17-121">안전 **링크** 정책 외부의 전역 설정에서 Office 365 앱에 대해 안전한 링크 보호를 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="95b17-121">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="95b17-122">자세한 내용은 [Office 365용 Microsoft Defender에서](configure-global-settings-for-safe-links.md)안전한 링크 설정에 대한 전역 설정 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-122">For instructions, see [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="95b17-123">그러나 Office 365 앱에 대한  안전한 링크 보호는 활성 안전 링크 정책에 포함된 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-123">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="95b17-124">사용자가 활성 안전 링크 정책에 포함되지 않은 경우 사용자는 지원되는 Office 365 앱에서 안전 링크 보호를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-124">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="95b17-125">Office 365 앱의 안전한 링크 보호에 대한 자세한 내용은 이 문서의 부분에 있는 [Office 365](#safe-links-settings-for-office-365-apps) 앱에 대한 안전 링크 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-125">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="95b17-126">이 문서에는 다음과 같은 유형의 안전 링크 설정에 대한 자세한 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-126">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="95b17-127">**안전한 링크** 정책의 설정: 이러한 설정은 특정 정책에 포함된 사용자에게만 적용될 수 있으며 정책 간에 설정이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-127">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="95b17-128">이러한 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-128">These settings include:</span></span>

  - [<span data-ttu-id="95b17-129">전자 메일 메시지에 대한 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="95b17-129">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="95b17-130">Microsoft Teams의 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="95b17-130">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="95b17-131">안전한 링크 정책에서 "다음 URL을 다시 덮어치지 않습니다." 목록</span><span class="sxs-lookup"><span data-stu-id="95b17-131">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="95b17-132">**전역 안전 링크 설정:** 이러한 설정은 안전한 링크 정책이 아니라 전역으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-132">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="95b17-133">그러나 설정은 활성 안전 링크 정책에 포함된 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-133">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="95b17-134">이러한 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-134">These settings include:</span></span>

  - [<span data-ttu-id="95b17-135">Office 365 앱의 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="95b17-135">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="95b17-136">안전한 링크에 대해 "다음 URL 차단" 목록</span><span class="sxs-lookup"><span data-stu-id="95b17-136">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="95b17-137">다음 표에서는 Office 365용 Defender를 포함 하는 Microsoft 365 및 Office 365 조직의 안전 링크에 대 한 시나리오에 설명 합니다(즉, 라이선스 부족은 예에서 문제가 아닙니다).</span><span class="sxs-lookup"><span data-stu-id="95b17-137">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="95b17-138">시나리오</span><span class="sxs-lookup"><span data-stu-id="95b17-138">Scenario</span></span>|<span data-ttu-id="95b17-139">결과</span><span class="sxs-lookup"><span data-stu-id="95b17-139">Result</span></span>|
|---|---|
|<span data-ttu-id="95b17-140">지민은 마케팅 부서의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-140">Jean is a member of the marketing department.</span></span> <span data-ttu-id="95b17-141">Office 365 앱에 대한 안전한 링크 보호는 안전한 링크에 대한 전역 설정에서 켜져 있으며 마케팅 부서의 구성원에게 적용되는 안전한 링크 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-141">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="95b17-142">전자 메일 메시지에 PowerPoint 프레젠테이션이 열리면 프레젠테이션의 URL을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-142">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="95b17-143">도장은 안전한 링크로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-143">Jean is protected by Safe Links.</span></span> <p> <span data-ttu-id="95b17-144">보관은 안전한 링크 정책에 포함되어 있으며 Office 365 앱에 대한 안전한 링크 보호가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-144">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <p> <span data-ttu-id="95b17-145">Office 365 앱에서 안전한 링크 보호를 위한 요구 사항에 대한 자세한 내용은 이 문서 부분의 [Office 365](#safe-links-settings-for-office-365-apps) 앱에 대한 안전 링크 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-145">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="95b17-146">Chris의 Microsoft 365 E5 조직에는 안전한 링크 정책이 구성되어 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-146">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="95b17-147">Chris는 최종적으로 클릭하는 악성 웹 사이트에 대한 URL이 포함된 외부 보낸 사람으로부터 전자 메일을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-147">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="95b17-148">Chris는 안전한 링크로 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-148">Chris is not protected by Safe Links.</span></span> <p> <span data-ttu-id="95b17-149">관리자는 인바운드 전자 메일 메시지에서 안전한 링크 보호를 받을 수 있도록 모든 사용자에 대해 하나 이상의 안전 링크 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-149">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="95b17-150">Chris는 안전한 링크 보호를 위해 정책 조건에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-150">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="95b17-151">Pat의 조직에서는 관리자가 안전한 링크 정책을 만들지 않지만 Office 365 앱에 대한 안전한 링크 보호가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-151">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="95b17-152">Pat에서 Word 문서를 열고 파일의 URL을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-152">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="95b17-153">Pat는 안전한 링크로 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-153">Pat is not protected by Safe Links.</span></span> <p> <span data-ttu-id="95b17-154">Office 365 앱에 대한 안전한 링크 보호는 전역으로 설정되어 있습니다. 그러나 Pat는 활성 안전 링크 정책에 포함되지 않습니다. 따라서 보호를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-154">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="95b17-155">이민호의 조직에서 안전한 링크에 대한 전역 설정의 다음 URL 차단 목록에서 `https://tailspintoys.com` 구성됩니다. </span><span class="sxs-lookup"><span data-stu-id="95b17-155">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="95b17-156">이민호를 포함하는 안전한 링크 정책이 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-156">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="95b17-157">이민호는 URL이 포함된 전자 메일 메시지를 `https://tailspintoys.com/aboutus/trythispage` 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-157">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="95b17-158">이민호는 URL을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-158">Lee clicks the URL.</span></span>|<span data-ttu-id="95b17-159">이민호의 URL이 자동으로 차단될 수 있습니다. 이 설정은 목록의 URL 항목과 이진호가 사용한 전자 메일 클라이언트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-159">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="95b17-160">자세한 내용은 이 문서 부분의 안전 링크 섹션에 대한 ["다음 URL 차단"](#block-the-following-urls-list-for-safe-links) 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-160">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this article.</span></span>|
|<span data-ttu-id="95b17-161">Jamie와 Julia는 둘 다 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="95b17-161">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="95b17-162">오래 전에 관리자는 Jamie와 Julia 모두에 적용되는 안전 링크 정책을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-162">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="95b17-163">Jamie는 전자 메일에 악의적인 URL이 포함되어 있는 것을 알지 못하고 조지민 에게 전자 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-163">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="95b17-164">조지민 의원에게  적용되는 안전한 링크 정책이 내부 받는 사람 간의 메시지에 적용하도록 구성된 경우 Julia는 안전한 링크로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-164">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="95b17-165">자세한 내용은 이 [](#safe-links-settings-for-email-messages) 문서 부분의 전자 메일 메시지에 대한 안전한 링크 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-165">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="95b17-166">전자 메일 메시지에 대한 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="95b17-166">Safe Links settings for email messages</span></span>

<span data-ttu-id="95b17-167">안전한 링크는 들어오는 전자 메일에서 알려진 악성 하이퍼링크를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-167">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="95b17-168">검사된 URL은 다음 Microsoft 표준 URL prefix를 사용하여 다시 덮어 `https://nam01.safelinks.protection.outlook.com` 습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-168">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="95b17-169">링크를 다시 덮어 입력하면 잠재적으로 악의적인 콘텐츠가 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-169">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="95b17-170">안전한 링크에서 URL을 다시 덮어도 메시지가 전달되거나 다시 덮어지지도 URL이 다시 덮어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-170">After Safe Links rewrites a URL, the URL remains rewritten, even if the message is forwarded or replied to.</span></span> <span data-ttu-id="95b17-171">전달되거나 메시지에 해당되는 추가 링크는 다시 덮어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-171">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span>

<span data-ttu-id="95b17-172">전자 메일 메시지에 적용되는 안전한 링크 정책의 설정은 다음 목록에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-172">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="95b17-173">**메시지에서** 알 수 없는 악의적인 URL에 대한 작업을 선택합니다. 전자 메일 메시지에서 안전한 링크 검색을 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="95b17-173">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="95b17-174">권장되는 값은 **On입니다.**</span><span class="sxs-lookup"><span data-stu-id="95b17-174">The recommended value is **On**.</span></span> <span data-ttu-id="95b17-175">이 설정을 켜면 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-175">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="95b17-176">안전 링크 검사는 Windows의 Outlook(C2R)에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-176">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="95b17-177">URL은 다시 덮어 사용하며 사용자는 메시지에서 URL을 클릭할 때 안전한 링크 보호를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-177">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="95b17-178">클릭하면 알려진 악성 URL 목록 및 "다음 URL 차단" 목록에 대해 URL이 [확인됩니다.](#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="95b17-178">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="95b17-179">유효한 신뢰도에 없는 URL은 백그라운드에서 비동기적으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-179">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="95b17-180">**파일을** 지정하는 의심스러운 링크 및 링크에 대한 실시간 URL 검색을 적용합니다. 다운로드 가능한 콘텐츠를 지정하는 전자 메일 메시지의 링크를 포함하여 링크를 실시간으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-180">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="95b17-181">권장되는 값은 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-181">The recommended value is enabled.</span></span>

  - <span data-ttu-id="95b17-182">**메시지를 배달하기 전에 URL 검색이 완료될 때까지 기다릴 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="95b17-182">**Wait for URL scanning to complete before delivering the message**:</span></span>

    - <span data-ttu-id="95b17-183">사용: URL이 포함된 메시지는 검사가 완료될 때까지 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-183">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="95b17-184">메시지는 URL이 안전한 것으로 확인된 후에만 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-184">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="95b17-185">이 값은 권장 값입니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-185">This is the recommended value.</span></span>
    - <span data-ttu-id="95b17-186">사용 안 하세요: URL 검색을 완료할 수 없는 경우 메시지를 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-186">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="95b17-187">**조직 내에서** 전송된 전자 메일 메시지에 안전한 링크 적용: 동일한 Exchange Online 조직 내의 내부 보낸 사람과 내부 받는 사람 간에 전송된 메시지에 대해 안전한 링크 검색을 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="95b17-187">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="95b17-188">권장되는 값은 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-188">The recommended value is enabled.</span></span>

- <span data-ttu-id="95b17-189">**사용자 클릭 추적** 안 하세요. 전자 메일 메시지에서 클릭한 URL에 대한 안전한 링크 클릭 데이터를 저장하거나 저장하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-189">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="95b17-190">권장 값은 이 설정을 선택하지 않은(사용자 클릭 추적)하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-190">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="95b17-191">내부 보낸 사람과 내부 받는 사람 간에 전송되는 전자 메일 메시지의 링크에 대한 URL 클릭 추적은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-191">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="95b17-192">**사용자가 원래 URL을 클릭할** 수 있도록 허용하지 않습니다. [](#warning-pages-from-safe-links) 사용자가 원래 URL에 대한 경고 페이지를 클릭할 수 있도록 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-192">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="95b17-193">권장 값을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-193">The recommend value is enabled.</span></span>

- <span data-ttu-id="95b17-194">**다음 URL을** 다시 덮어치지 않습니다. URL을 그대로 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-194">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="95b17-195">검사할 필요가 없는 안전한 URL의 사용자 지정 목록을 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-195">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="95b17-196">이 목록은 각 안전 링크 정책에 대해 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-196">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="95b17-197">다음 URL 목록을  다시 덮어치지 않는 자세한 내용은 이 문서 부분의 안전 링크 정책 섹션에서 ["다음 URL을](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 다시 덮어치지 않습니다." 목록을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95b17-197">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="95b17-198">안전 링크 정책에 대한 표준 및 엄격한 정책 설정에 대한 권장 값에 대한 자세한 내용은 안전 링크 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="95b17-198">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="95b17-199">**받는 사람 필터:** 정책을 적용하는 사람을 결정하는 받는 사람 조건 및 예외를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-199">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="95b17-200">조건 및 예외에 대해 다음 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-200">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="95b17-201">**받는 사람이 다음과 같음**</span><span class="sxs-lookup"><span data-stu-id="95b17-201">**The recipient is**</span></span>
  - <span data-ttu-id="95b17-202">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="95b17-202">**The recipient domain is**</span></span>
  - <span data-ttu-id="95b17-203">**받는 사람이 다음의 구성원임**</span><span class="sxs-lookup"><span data-stu-id="95b17-203">**The recipient is a member of**</span></span>

  <span data-ttu-id="95b17-204">조건 또는 예외는 한 번만 사용할 수 있지만 조건 또는 예외에 여러 값이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-204">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="95b17-205">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="95b17-205">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="95b17-206">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="95b17-206">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="95b17-207">**우선** 순위: 여러 정책을 만드는 경우 정책이 적용되는 순서를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-207">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="95b17-208">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-208">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="95b17-209">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-209">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="95b17-210">전자 메일 메시지에서 안전한 링크가 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="95b17-210">How Safe Links works in email messages</span></span>

<span data-ttu-id="95b17-211">높은 수준에서 안전한 링크 보호가 전자 메일 메시지의 URL에서 작동하는 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-211">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="95b17-212">모든 전자 메일은 메시지가 받는 사람의 사서함으로 배달되기 전에 IP(인터넷 프로토콜) 및 봉투 필터, 서명 기반 맬웨어 보호, 스팸 방지 및 맬웨어 방지 필터가 있는 EOP를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-212">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="95b17-213">사용자가 사서함에서 메시지를 열고 메시지의 URL을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-213">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="95b17-214">안전한 링크는 웹 사이트를 열기 전에 URL을 즉시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-214">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="95b17-215">URL이 다음 URL  차단 목록에 포함되어 있는 경우 차단된 [URL 경고가](#blocked-url-warning) 열립니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-215">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="95b17-216">URL이 악성으로 확인된 웹 사이트를 표시하면 [](#malicious-website-warning) 악성 웹 사이트 경고 페이지(또는 다른 경고 페이지)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-216">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="95b17-217">URL이 다운로드 가능한 파일을 지정하고 파일 설정을 지정하는 실시간 **URL** 적용 검색이 사용자에게 적용되는 정책에서 사용하도록 설정되어 있는 경우 다운로드 가능한 파일이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-217">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="95b17-218">URL이 안전한 것으로 확인되면 웹 사이트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-218">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="95b17-219">Microsoft Teams의 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="95b17-219">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95b17-220">2020년 3월 현재 이 기능은 미리 보기로 제공된 기능으로, TAP(Microsoft Teams Technology Adoption Program)의 구성원만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-220">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="95b17-221">릴리스 일정에 대한 자세한 내용은 [Microsoft 365 로드맵을 참조하십시오.](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)</span><span class="sxs-lookup"><span data-stu-id="95b17-221">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="95b17-222">안전한 링크 정책에서 Microsoft Teams에 대해 안전한 링크 보호를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-222">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="95b17-223">특히 Microsoft Teams 설정 내에서 알 수 없는 URL이나 악의적인 **URL에** 대한 선택 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-223">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="95b17-224">권장되는 값은 **On입니다.**</span><span class="sxs-lookup"><span data-stu-id="95b17-224">The recommended value is **On**.</span></span>

<span data-ttu-id="95b17-225">전자 메일 메시지의 링크에 적용되는 안전한 링크 정책의 다음 설정은 Teams의 링크에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-225">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="95b17-226">**파일을 지정하는 의심스러운 링크 및 링크에 대한 실시간 URL 검사 적용**</span><span class="sxs-lookup"><span data-stu-id="95b17-226">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="95b17-227">**사용자 클릭 추적 안 하도록 설정**</span><span class="sxs-lookup"><span data-stu-id="95b17-227">**Do not track user clicks**</span></span>
- <span data-ttu-id="95b17-228">**사용자가 원래 URL을 클릭할 수 있도록 허용 안 하세요.**</span><span class="sxs-lookup"><span data-stu-id="95b17-228">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="95b17-229">이러한 설정은 전자 메일 메시지에 대한 이전 안전 링크 설정 [섹션에서 설명합니다.](#safe-links-settings-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="95b17-229">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="95b17-230">Microsoft Teams에 대해 안전한 링크 보호를 켜면 보호된 사용자가 링크를 클릭할 때 Teams의 URL이 알려진 악성 링크 목록에 대해 확인됩니다(클릭 시간 보호).</span><span class="sxs-lookup"><span data-stu-id="95b17-230">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="95b17-231">URL은 다시 덮어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-231">URLs are not rewritten.</span></span> <span data-ttu-id="95b17-232">링크가 악성으로 확인된 경우 사용자는 다음과 같은 경험을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-232">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="95b17-233">링크가 Teams 대화, 그룹 채팅 또는 채널에서 클릭된 경우 아래 스크린샷에 표시된 경고 페이지가 기본 웹 브라우저에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-233">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="95b17-234">고정된 탭에서 링크를 클릭한 경우 해당 탭 내의 Teams 인터페이스에 경고 페이지가 표시됩니다. 보안상의 이유로 웹 브라우저에서 링크를 여는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-234">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="95b17-235">사용자가 정책의 원래 URL 설정을 클릭할 수 있도록 허용하지 않는 방법에 따라 사용자는 원래 **URL(스크린샷에서** 권장되지 않음)을 클릭할 수 있는지 또는 클릭할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-235">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="95b17-236">사용자가 원래 **URL을** 클릭할 수 없는 원래 URL 설정을 클릭하지 못하도록 허용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-236">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="95b17-237">링크를 보낸 사용자가 Teams 보호가 설정된 안전한 링크 정책에 포함되지 않은 경우 사용자는 컴퓨터 또는 장치의 원래 URL을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-237">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![악의적인 링크를 보고하는 Teams의 안전한 링크입니다.](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="95b17-239">경고 페이지에서 **뒤로 이동** 단추를 클릭하면 사용자가 원래 컨텍스트 또는 URL 위치로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-239">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="95b17-240">그러나 원래 링크를 다시 클릭하면 안전한 링크가 URL을 다시 검색할 수 있으므로 경고 페이지가 다시 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-240">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="95b17-241">Teams에서 안전한 링크가 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="95b17-241">How Safe Links works in Teams</span></span>

<span data-ttu-id="95b17-242">Microsoft Teams의 URL에 대해 안전한 링크 보호가 작동하는 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-242">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="95b17-243">사용자가 Teams 앱을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-243">A user starts the Teams app.</span></span>

2. <span data-ttu-id="95b17-244">Microsoft 365는 사용자의 조직에 Office 365용 Microsoft Defender가 포함되어 있으며 Microsoft Teams에 대한 보호가 설정된 활성 안전 링크 정책에 해당 사용자가 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-244">Microsoft 365 verifies that the user's organization includes Microsoft Defender for Office 365, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="95b17-245">채팅, 그룹 채팅, 채널 및 탭에서 사용자를 클릭할 때 URL의 유효성이 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-245">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="95b17-246">Office 365 앱의 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="95b17-246">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="95b17-247">Office 365 앱의 안전한 링크 보호는 전자 메일 메시지의 링크가 아닌 Office 문서의 링크를 검사합니다(문서가 열리면 전자 메일 메시지에 첨부된 Office 문서의 링크를 확인할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="95b17-247">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="95b17-248">Office 365 앱의 안전한 링크 보호에는 다음과 같은 클라이언트 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-248">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="95b17-249">Microsoft 365 앱 또는 Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="95b17-249">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="95b17-250">Windows, Mac 또는 웹 브라우저의 현재 버전의 Word, Excel 및 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="95b17-250">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="95b17-251">iOS 또는 Android 장치의 Office 앱.</span><span class="sxs-lookup"><span data-stu-id="95b17-251">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="95b17-252">Windows의 Visio.</span><span class="sxs-lookup"><span data-stu-id="95b17-252">Visio on Windows.</span></span>
  - <span data-ttu-id="95b17-253">웹 브라우저의 OneNote.</span><span class="sxs-lookup"><span data-stu-id="95b17-253">OneNote in a web browser.</span></span>

- <span data-ttu-id="95b17-254">Office 365 앱은 최신 인증을 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-254">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="95b17-255">자세한 내용은 [Office 2013, Office 2016 및 Office 2019](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)클라이언트 앱에 대해 최신 인증이 작동하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-255">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span>

- <span data-ttu-id="95b17-256">사용자는 자신의 직장 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-256">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="95b17-257">자세한 내용은 [Office에 로그인을 참조하세요.](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)</span><span class="sxs-lookup"><span data-stu-id="95b17-257">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="95b17-258">안전한 링크 정책이 아니라 안전한 링크에 대한 전역 설정에서 Office 365 앱에 대한 안전한 링크 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-258">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="95b17-259">그러나 Office 365 앱에 대한 안전한 링크 보호를 적용하려면 Office 문서를 열고 링크를 클릭하는 사용자가 활성 안전 링크 정책에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-259">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="95b17-260">Office 365 앱에서 사용할 수 있는 안전한 링크 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-260">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="95b17-261">**Office 365 응용 프로그램:** 지원되는 Office 365 앱에서 안전한 링크 검색을 활성화 또는 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-261">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="95b17-262">기본값과 권장 값은 **On입니다.**</span><span class="sxs-lookup"><span data-stu-id="95b17-262">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="95b17-263">**사용자가 안전한** 링크를 클릭하는 경우를 추적하지 않습니다. 데스크톱 버전 Word, Excel, PowerPoint 및 Visio에서 클릭한 URL에 대한 안전한 링크 클릭 데이터를 저장하거나 저장하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-263">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="95b17-264">권장되는 값은 **Off입니다.** 즉, 사용자 클릭이 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-264">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="95b17-265">**사용자가 원래 URL에** 대한 안전한 링크를 클릭할 수 있도록 허용하지 않습니다. 사용자가 데스크톱 버전 Word, Excel, PowerPoint 및 Visio에서 원래 URL에 대한 경고 페이지를 클릭하지 못하게 허용하거나 차단합니다. [](#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="95b17-265">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="95b17-266">기본값과 권장 값은 **On입니다.**</span><span class="sxs-lookup"><span data-stu-id="95b17-266">The default and recommended value is **On**.</span></span>

<span data-ttu-id="95b17-267">Office 365 앱에 대한 안전한 링크 설정을 구성하려면 Office 365 앱에 대한 안전한 링크 보호 [구성을 참조하세요.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)</span><span class="sxs-lookup"><span data-stu-id="95b17-267">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="95b17-268">표준 및 엄격 정책 설정의 권장 값에 대한 자세한 내용은 안전 링크에 대한 전역 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="95b17-268">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="95b17-269">Office 365 앱에서 안전한 링크가 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="95b17-269">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="95b17-270">Office 365 앱에서 URL에 대해 안전한 링크 보호가 작동하는 방식은 다음과 같은 높은 수준에서 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-270">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="95b17-271">지원되는 Office 365 앱은 이전 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-271">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="95b17-272">사용자가 Microsoft 365 앱 또는 Microsoft 365 Business Premium을 포함하는 조직에서 직장 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-272">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="95b17-273">사용자가 지원되는 Office 앱에서 Office 문서를 열고 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-273">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="95b17-274">안전한 링크는 대상 웹 사이트를 열기 전에 URL을 즉시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-274">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="95b17-275">안전한 링크 검색(다음 URL 목록 **차단)을** 건너뛰는 목록에 URL이 포함되어 있는 경우 [차단된 URL](#blocked-url-warning) 경고 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-275">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="95b17-276">URL이 악성으로 확인된 웹 사이트를 표시하면 [](#malicious-website-warning) 악성 웹 사이트 경고 페이지(또는 다른 경고 페이지)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-276">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="95b17-277">URL이 다운로드 가능한 파일을, 그리고 사용자에게 적용되는 안전한 링크 정책이 다운로드 가능한 콘텐츠에 대한 링크를 검색하도록 구성되어 있는 경우(의심스러운 링크 및 파일을 지정하는 링크를 위한 실시간 **URL** 검색 적용), 다운로드 가능한 파일이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-277">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="95b17-278">URL이 안전한 것으로 간주되는 경우 사용자는 웹 사이트로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-278">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="95b17-279">안전한 링크 검색을 완료할 수 없는 경우 안전한 링크 보호가 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-279">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="95b17-280">Office 데스크톱 클라이언트에서는 대상 웹 사이트로 이동하기 전에 사용자에게 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-280">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="95b17-281">각 세션이 시작될 때 사용자에게 Office용 안전 링크가 설정되어 있는지 확인하는 데 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-281">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="95b17-282">안전한 링크에 대해 "다음 URL 차단" 목록</span><span class="sxs-lookup"><span data-stu-id="95b17-282">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="95b17-283">다음 URL 차단 **목록은** 다음 위치에서 안전 링크 검색에 의해 항상 차단되는 링크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-283">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="95b17-284">전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-284">Email messages.</span></span>
- <span data-ttu-id="95b17-285">Windows 및 Mac의 Office 365 앱에 있는 문서.</span><span class="sxs-lookup"><span data-stu-id="95b17-285">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="95b17-286">iOS 및 Android용 Office의 문서.</span><span class="sxs-lookup"><span data-stu-id="95b17-286">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="95b17-287">활성 안전 링크 정책의 사용자가 지원되는 앱에서 차단된 링크를 클릭하면 차단된 URL 경고 [페이지로 이동됩니다.](#blocked-url-warning)</span><span class="sxs-lookup"><span data-stu-id="95b17-287">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="95b17-288">안전한 링크에 대한 전역 설정에서 URL 목록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-288">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="95b17-289">자세한 내용은 ["다음 URL 차단" 목록](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-289">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="95b17-290">**참고**:</span><span class="sxs-lookup"><span data-stu-id="95b17-290">**Notes**:</span></span>

- <span data-ttu-id="95b17-291">모든 곳에서 차단되는 URL의 진정한 범용 목록은 테넌트 [허용/차단 목록 관리를 참조하세요.](tenant-allow-block-list.md)</span><span class="sxs-lookup"><span data-stu-id="95b17-291">For a truly universal list of URLs that are blocked everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="95b17-292">제한:</span><span class="sxs-lookup"><span data-stu-id="95b17-292">Limits:</span></span>
  - <span data-ttu-id="95b17-293">최대 항목 수는 500개입니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-293">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="95b17-294">항목의 최대 길이는 128자입니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-294">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="95b17-295">모든 항목은 10,000자까지 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-295">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="95b17-296">URL의 끝에 `/` 슬래시()를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-296">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="95b17-297">예를 들어 `https://www.contoso.com` 다음을 사용하지 `https://www.contoso.com/` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-297">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="95b17-298">도메인 전용 URL(예: 또는 )은 도메인이 포함된 `contoso.com` `tailspintoys.com` 모든 URL을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-298">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="95b17-299">전체 도메인을 차단하지 않고 하위 도메인을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-299">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="95b17-300">예를 들어 하위 도메인이 포함된 URL은 차단하지만 전체 도메인을 포함하는 `toys.contoso.com*` URL은 차단하지 `contoso.com` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-300">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="95b17-301">URL 항목당 와일드카드()를 `*` 세 개까지 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-301">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="95b17-302">"다음 URL 차단" 목록에 대한 항목 구문</span><span class="sxs-lookup"><span data-stu-id="95b17-302">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="95b17-303">다음 표에는 입력할 수 있는 값과 해당 결과가 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-303">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="95b17-304">값</span><span class="sxs-lookup"><span data-stu-id="95b17-304">Value</span></span>|<span data-ttu-id="95b17-305">결과</span><span class="sxs-lookup"><span data-stu-id="95b17-305">Result</span></span>|
|---|---|
|`contoso.com` <p> <span data-ttu-id="95b17-306">또는</span><span class="sxs-lookup"><span data-stu-id="95b17-306">or</span></span> <p> `*contoso.com*`|<span data-ttu-id="95b17-307">도메인, 하위 도메인 및 경로를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-307">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="95b17-308">예를 들어 `https://www.contoso.com` `https://sub.contoso.com` `https://contoso.com/abc` 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-308">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="95b17-309">처럼 `https://contoso.com/a` 추가 하위 경로는 차단하지만 차단하지는 `https://contoso.com/a/b` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-309">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="95b17-310">처럼 `https://contoso.com/a` 블록 및 추가 하위 `https://contoso.com/a/b` 경로</span><span class="sxs-lookup"><span data-stu-id="95b17-310">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="95b17-311">하위 도메인(이 예의 경우)을 차단하지만 다른 도메인 URL(예: 또는 )을 클릭할 수 `toys` `https://contoso.com` `https://home.contoso.com` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-311">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="95b17-312">안전한 링크 정책에서 "다음 URL을 다시 덮어치지 않습니다." 목록</span><span class="sxs-lookup"><span data-stu-id="95b17-312">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="95b17-313">조직에서 안전한 링크 정책을  사용하는 경우 다음 URL 목록을 다시 기록하지 않는 것이 타사 피싱 테스트에 대해 지원되는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-313">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="95b17-314">각 안전 링크  정책에는 안전 링크 검색을 통해 다시 덮어지지 않는 URL을 지정하는 데 사용할 수 있는 다음 URL 목록을 다시 덮어치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-314">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="95b17-315">즉, 이 목록을 사용하면 정책에 포함된 사용자가 안전한 링크로 차단되는 지정된 URL에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-315">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="95b17-316">서로 다른 안전 링크 정책에서 서로 다른 목록을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-316">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="95b17-317">정책 처리는 사용자에게 첫 번째(우선 순위가 가장 높은) 정책이 적용된 후 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-317">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="95b17-318">따라서 여러 활성 안전 링크 정책에 포함된 사용자에게는 다음 **URL** 목록을 다시 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-318">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="95b17-319">새 정책 또는 기존 안전 링크 정책의 목록에 항목을 추가하려면 안전한 링크 만들기 정책 [또는](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 안전 링크 수정 [정책을 참조하세요.](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="95b17-319">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="95b17-320">**참고**:</span><span class="sxs-lookup"><span data-stu-id="95b17-320">**Notes**:</span></span>

- <span data-ttu-id="95b17-321">다음 클라이언트는 안전 링크 정책에서 다음 **URL** 목록을 다시 덮어 들이지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-321">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="95b17-322">이러한 클라이언트에서 안전한 링크 검색 결과를 기반으로 하여, 보안에 포함된 사용자는 URL에 액세스하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-322">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="95b17-323">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95b17-323">Microsoft Teams</span></span>
  - <span data-ttu-id="95b17-324">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="95b17-324">Office web apps</span></span>

  <span data-ttu-id="95b17-325">모든 곳에서 허용되는 진정한 범용 URL 목록은 테넌트 [허용/차단 목록 관리를 참조하세요.](tenant-allow-block-list.md)</span><span class="sxs-lookup"><span data-stu-id="95b17-325">For a truly universal list of URLs that are allowed everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="95b17-326">사용자 환경을 개선하기 위해 일반적으로 사용되는 내부 URL을 목록에 추가하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-326">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="95b17-327">예를 들어 비즈니스용 Skype 또는 SharePoint와 같은 프레미스 서비스가 있는 경우 해당 URL을 추가하여 검색에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-327">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="95b17-328">안전 링크 정책에서 다음 **URL** 항목을 이미 다시 작성하지 않은 경우 목록을 검토하고 필요한 경우 와일드카드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-328">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="95b17-329">예를 들어 목록에 다음과 같은 항목이 있으며 나중에 다음과 같은 하위 경로가 `https://contoso.com/a` 포함될 수 `https://contoso.com/a/b` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-329">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="95b17-330">새 항목을 추가하는 대신 기존 항목에 와일드카드를 추가하여 기존 항목이 `https://contoso.com/a/*` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-330">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="95b17-331">URL 항목당 와일드카드()를 `*` 세 개까지 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-331">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="95b17-332">와일드카드에는 명시적으로 prefixes 또는 subdomains가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-332">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="95b17-333">예를 들어 사용자가 지정된 도메인의 하위 도메인 및 경로를 방문할 수 있기 때문에 항목은 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-333">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="95b17-334">"다음 URL을 다시 덮어치지 않습니다." 목록에 대한 항목 구문</span><span class="sxs-lookup"><span data-stu-id="95b17-334">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="95b17-335">다음 표에는 입력할 수 있는 값과 해당 결과가 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-335">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="95b17-336">값</span><span class="sxs-lookup"><span data-stu-id="95b17-336">Value</span></span>|<span data-ttu-id="95b17-337">결과</span><span class="sxs-lookup"><span data-stu-id="95b17-337">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="95b17-338">하위omain 또는 경로에는 액세스할 수 있지만 액세스할 `https://contoso.com` 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-338">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="95b17-339">도메인, 하위 도메인 및 경로(예: , 또는 )에 대한 액세스를 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-339">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <p> <span data-ttu-id="95b17-340">이 항목은 다음 항목보다 본질적으로 더 좋습니다. 이러한 항목은 또는 `*contoso.com*` `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="95b17-340">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="95b17-341">하위 경로에 대한 액세스를 허용하지만 같은 `https://contoso.com/a` 하위 경로는 허용하지 않습니다. `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="95b17-341">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="95b17-342">같은 하위 경로 `https://contoso.com/a` 및 액세스 허용 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="95b17-342">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="95b17-343">안전한 링크의 경고 페이지</span><span class="sxs-lookup"><span data-stu-id="95b17-343">Warning pages from Safe Links</span></span>

<span data-ttu-id="95b17-344">이 섹션에는 URL을 클릭할 때 안전한 링크 보호에 의해 트리거되는 다양한 경고 페이지의 예가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-344">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="95b17-345">여러 경고 페이지가 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-345">Note that several warning pages have been updated.</span></span> <span data-ttu-id="95b17-346">업데이트된 페이지가 아직 없는 경우 곧 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-346">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="95b17-347">업데이트된 페이지에는 새로운 색 구성표, 세부 정보 및 제공된 경고 및 권장 사항에도 불구하고 사이트로 진행할 수 있는 능력이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-347">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="95b17-348">검사 진행 중 알림</span><span class="sxs-lookup"><span data-stu-id="95b17-348">Scan in progress notification</span></span>

<span data-ttu-id="95b17-349">클릭한 URL이 안전한 링크로 검색되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-349">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="95b17-350">링크를 다시 시도하기 전에 몇 분 정도 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-350">You might need to wait a few moments before trying the link again.</span></span>

!["링크가 검사 중입니다." 알림](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="95b17-352">원래 알림 페이지는 다음과 같이 표시했습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-352">The original notification page looked like this:</span></span>

![원래 "링크가 검색되고 있습니다." 알림](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="95b17-354">의심스러운 메시지 경고</span><span class="sxs-lookup"><span data-stu-id="95b17-354">Suspicious message warning</span></span>

<span data-ttu-id="95b17-355">클릭한 URL은 다른 의심스러운 메시지와 유사한 전자 메일 메시지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-355">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="95b17-356">사이트로 진행하기 전에 전자 메일 메시지를 다시 검사하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-356">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["의심스러운 메시지에서 링크를 클릭했습니다." 경고](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="95b17-358">피싱 시도 경고</span><span class="sxs-lookup"><span data-stu-id="95b17-358">Phishing attempt warning</span></span>

<span data-ttu-id="95b17-359">클릭한 URL은 피싱 공격으로 식별된 전자 메일 메시지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-359">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="95b17-360">따라서 전자 메일 메시지의 모든 URL이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-360">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="95b17-361">사이트로 진행하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-361">We recommend that you do not proceed to the site.</span></span>

!["링크가 피싱 메시지에서 클릭된 경우" 경고](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="95b17-363">악성 웹 사이트 경고</span><span class="sxs-lookup"><span data-stu-id="95b17-363">Malicious website warning</span></span>

<span data-ttu-id="95b17-364">클릭한 URL은 악의적인 것으로 식별된 사이트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-364">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="95b17-365">사이트로 진행하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-365">We recommend that you do not proceed to the site.</span></span>

!["이 웹 사이트는 악성으로 분류됩니다." 경고](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="95b17-367">원래 경고 페이지는 다음과 같이 표시했습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-367">The original warning page looked like this:</span></span>

![원래 "이 웹 사이트가 악성으로 분류" 경고](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="95b17-369">차단된 URL 경고</span><span class="sxs-lookup"><span data-stu-id="95b17-369">Blocked URL warning</span></span>

<span data-ttu-id="95b17-370">클릭한 URL은 조직의 관리자가 수동으로 차단했습니다(안전한 링크에 대한 전역 설정의 다음 **URL** 차단 목록).</span><span class="sxs-lookup"><span data-stu-id="95b17-370">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="95b17-371">링크가 수동으로 차단된 것이기 때문에 안전한 링크에서 링크를 검색하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-371">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="95b17-372">관리자가 특정 URL을 수동으로 차단하는 이유는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-372">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="95b17-373">사이트가 차단되지 않을 것으로 생각되는 경우 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="95b17-373">If you think the site should not be blocked, contact your admin.</span></span>

!["이 웹 사이트가 관리자가 차단했습니다." 경고](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="95b17-375">원래 경고 페이지는 다음과 같이 표시했습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-375">The original warning page looked like this:</span></span>

![원래 "이 웹 사이트가 조직의 URL 정책에 따라 차단했습니다." 경고](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="95b17-377">오류 경고</span><span class="sxs-lookup"><span data-stu-id="95b17-377">Error warning</span></span>

<span data-ttu-id="95b17-378">일부 오류가 발생하여 URL을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-378">Some kind of error has occurred, and the URL can't be opened.</span></span>

!["액세스하려는 페이지를 로드할 수 없습니다." 경고](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="95b17-380">원래 경고 페이지는 다음과 같이 표시했습니다.</span><span class="sxs-lookup"><span data-stu-id="95b17-380">The original warning page looked like this:</span></span>

![원래 "이 웹 페이지를 로드할 수 없습니다." 경고](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
