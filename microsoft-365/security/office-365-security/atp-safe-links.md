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
ms.service: O365-seccomp
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
description: 이 문서에서는 관리자가 악성 Url을 사용 하는 피싱 및 기타 공격 으로부터 조직을 보호 하기 위해 Office 365 ATP (Advanced Threat Protection)의 안전한 링크 보호에 대해 알아볼 수 있습니다.
ms.openlocfilehash: d4c939d45818ba14c4407eee063aca46e4ee5b03
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447098"
---
# <a name="safe-links-in-office-365-atp"></a><span data-ttu-id="57181-103">Office 365 ATP의 안전한 링크</span><span class="sxs-lookup"><span data-stu-id="57181-103">Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="57181-104">이 문서는 [Office 365 ATP (Advanced Threat Protection)](office-365-atp.md)가 있는 비즈니스 고객을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="57181-105">Outlook.com, Microsoft 365 제품군 또는 Microsoft 365 Personal을 사용 하 고 있고 Outlook의 Safelinks에 대 한 정보를 찾으려는 경우 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57181-105">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="57181-106">안전한 링크는 메일 흐름에서 인바운드 전자 메일 메시지에 대 한 URL 검색 및 다시 쓰기를 제공 하 고 전자 메일 메시지와 기타 위치의 Url 및 링크에 대 한 클릭 하는 방법으로, [Office 365 Advanced Threat Protection](office-365-atp.md) 의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-106">Safe Links is a feature in [Office 365 Advanced Threat Protection](office-365-atp.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="57181-107">안전한 링크 검색은 EOP (Exchange Online Protection)의 인바운드 전자 메일 메시지에 있는 일반 [스팸 방지 및 맬웨어 방지 보호 기능](anti-spam-and-anti-malware-protection.md) 외에도 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-107">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="57181-108">안전한 링크 검색 기능은 피싱 및 기타 공격에 사용 되는 악의적인 링크 로부터 조직을 보호 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-108">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="57181-109">안전한 링크 보호는 다음 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-109">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="57181-110">**전자 메일 메시지**: 전자 메일 메시지의 링크에 대 한 안전한 링크 보호는 안전한 링크 정책에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-110">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="57181-111">안전한 링크 정책 없이도 **전자 메일 메시지의 안전한 링크를 보호 하려면 하나 이상의 안전한 링크 정책을 만들어야**합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-111">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="57181-112">자세한 내용은 [ATP에서 안전한 링크 정책 설정을](set-up-atp-safe-links-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-112">For instructions, see [Set up Safe Links policies in ATP](set-up-atp-safe-links-policies.md).</span></span>

  <span data-ttu-id="57181-113">전자 메일 메시지에 대 한 안전한 링크 보호에 대 한 자세한 내용은이 문서 뒷부분의 [전자 메일 메시지에 대 한 안전한 링크 설정](#safe-links-settings-for-email-messages) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-113">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="57181-114">**Microsoft 팀** (현재 탭 미리 보기): 팀 대화, 그룹 채팅 또는 채널의 링크에 대 한 안전한 링크 보호도 안전한 링크 정책에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-114">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="57181-115">안전한 링크 정책이 없는 경우 **팀의 안전한 링크를 보호 하려면 하나 이상의 안전한 링크 정책을 만들어야**합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-115">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="57181-116">팀의 안전한 링크 보호에 대 한 자세한 내용은이 항목 뒷부분의 [Microsoft 팀에 대 한 안전한 링크 설정](#safe-links-settings-for-microsoft-teams) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-116">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this topic.</span></span>

- <span data-ttu-id="57181-117">**Office 365 앱**: office 365 앱에 대 한 안전한 링크 보호는 지원 되는 데스크톱, 모바일 및 웹 ap에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-117">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="57181-118">안전한 링크 정책을 **벗어나는** 전역 설정에서 Office 365 앱에 대 한 안전한 링크 보호를 **구성** 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-118">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="57181-119">자세한 내용은 [Office 365 ATP에서 안전한 링크 설정에 대 한 전역 설정 구성을](configure-global-settings-for-safe-links.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-119">For instructions, see [Configure global settings for Safe Links settings in Office 365 ATP](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="57181-120">그러나 Office 365 앱에 대 한 안전한 링크 보호는 활성 안전한 링크 정책에 포함 된 사용자 에게만 **적용** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-120">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="57181-121">활성 안전한 링크 정책에 사용자가 포함 되어 있지 않으면 사용자가 지원 되는 Office 365 앱에서 안전한 링크 보호를 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-121">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="57181-122">Office 365 앱의 안전한 링크 보호에 대 한 자세한 내용은이 문서 뒷부분에 있는 [office 365 앱에 대 한 안전한 링크 설정](#safe-links-settings-for-office-365-apps) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-122">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="57181-123">이 문서에는 다음과 같은 유형의 안전한 링크 설정에 대 한 자세한 설명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-123">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="57181-124">**안전한 링크 정책의 설정**: 이러한 설정은 특정 정책에 포함 된 사용자 에게만 적용 되며 정책 간에는 설정이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-124">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="57181-125">이러한 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-125">These settings include:</span></span>

  - [<span data-ttu-id="57181-126">전자 메일 메시지에 대 한 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="57181-126">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="57181-127">Microsoft 팀에 대 한 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="57181-127">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="57181-128">안전한 링크 정책의 "다음 Url을 다시 쓰지 않음" 목록</span><span class="sxs-lookup"><span data-stu-id="57181-128">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="57181-129">**전역 안전 링크 설정**: 이러한 설정은 안전한 링크 정책이 아닌 전역적으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-129">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="57181-130">그러나이 설정은 활성 안전한 링크 정책에 포함 된 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-130">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="57181-131">이러한 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-131">These settings include:</span></span>

  - [<span data-ttu-id="57181-132">Office 365 앱에 대 한 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="57181-132">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="57181-133">안전한 링크에 대 한 "다음 Url 차단" 목록</span><span class="sxs-lookup"><span data-stu-id="57181-133">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="57181-134">다음 표에서는 ATP를 포함 하는 Microsoft 365 및 Office 365 조 직의 안전한 링크에 대 한 시나리오를 설명 합니다 (즉, 라이선스 부족은 해당 예에서 문제가 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="57181-134">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include ATP (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="57181-135">시나리오</span><span class="sxs-lookup"><span data-stu-id="57181-135">Scenario</span></span>|<span data-ttu-id="57181-136">결과</span><span class="sxs-lookup"><span data-stu-id="57181-136">Result</span></span>|
|---|---|
|<span data-ttu-id="57181-137">Jean은 마케팅 부서의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-137">Jean is a member of the marketing department.</span></span> <span data-ttu-id="57181-138">안전한 링크 보호 Office 365 앱은 안전한 링크에 대 한 전역 설정에 설정 되어 있으며, 마케팅 부서의 구성원에 게 적용 되는 안전한 링크 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-138">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="57181-139">Jean에서 PowerPoint 프레젠테이션을 전자 메일 메시지로 열고 프레젠테이션에서 URL을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-139">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="57181-140">Jean는 안전한 링크로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-140">Jean is protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="57181-141">Jean는 안전한 링크 정책에 포함 되어 있으며 Office 365 앱에 대 한 안전한 링크 보호 기능이 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-141">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <br/><br/> <span data-ttu-id="57181-142">Office 365 앱의 안전한 링크 보호 요구 사항에 대 한 자세한 내용은이 문서 뒷부분의 [office 365 apps에 대 한 안전한 링크 설정](#safe-links-settings-for-office-365-apps) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-142">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="57181-143">Chris의 Microsoft 365 E5 조직에는 구성 된 안전한 링크 정책이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-143">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="57181-144">Chris는 궁극적으로 클릭 하는 악성 웹 사이트에 대 한 URL이 포함 된 외부 보낸 사람의 전자 메일을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-144">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="57181-145">Chris가 안전한 링크를 통해 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-145">Chris is not protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="57181-146">관리자는 인바운드 전자 메일 메시지에서 안전한 링크 보호를 가져올 수 있도록 모든 사용자에 대해 하나 이상의 안전한 링크 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-146">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="57181-147">안전한 링크 보호를 얻으려면 정책 조건에 Chris가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-147">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="57181-148">Pat의 조직에서는 관리자가 안전한 링크 정책을 만들지 않았지만 Office 365 앱에 대 한 안전한 링크 보호가 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-148">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="57181-149">Word 문서를 열고 파일의 URL을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-149">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="57181-150">Pat가 안전한 링크로 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-150">Pat is not protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="57181-151">Office 365 앱에 대 한 안전한 링크 보호 기능은 전역적으로 켜져 있지만, Pat는 활성 안전한 링크 정책에 포함 되어 있지 않으므로 보호 기능을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-151">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="57181-152">Lee 조직의 조직에서 `https://tailspintoys.com` 안전한 링크에 대 한 전역 설정의 **다음 url 차단** 목록에 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-152">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="57181-153">Lee이 포함 된 안전한 링크 정책이 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-153">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="57181-154">Lee에서 URL을 포함 하는 전자 메일 메시지를 받습니다 `https://tailspintoys.com/aboutus/trythispage` .</span><span class="sxs-lookup"><span data-stu-id="57181-154">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="57181-155">Lee에서 URL을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-155">Lee clicks the URL.</span></span>|<span data-ttu-id="57181-156">URL이 Lee에 대해 자동으로 차단 될 수 있습니다. 이는 목록의 URL 항목과 사용 되는 전자 메일 클라이언트 Lee에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="57181-156">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="57181-157">자세한 내용은이 항목 뒷부분에 나오는 ["다음 Url 차단" 안전한 링크에 대 한 목록](#block-the-following-urls-list-for-safe-links) 보기 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-157">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this topic.</span></span>|
|<span data-ttu-id="57181-158">Contoso.com에 대해 작업자와 줄리아가 모두 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-158">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="57181-159">오랜 시간 전에 관리자가 구성한 안전한 링크 정책이 김 및 줄리아 모두에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-159">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="57181-160">이 전자 메일에 악성 URL이 포함 되어 있다는 것을 모르는 경우에는 전자 메일이 줄리아로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-160">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="57181-161">줄리아는 안전한 링크 정책이 내부 받는 사람 간의 메시지에 적용 되도록 구성 된 **경우** 안전 링크에 의해 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-161">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="57181-162">자세한 내용은이 항목 뒷부분에 나오는 [전자 메일 메시지에 대 한 안전한 링크 설정](#safe-links-settings-for-email-messages) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-162">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this topic.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="57181-163">전자 메일 메시지에 대 한 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="57181-163">Safe Links settings for email messages</span></span>

<span data-ttu-id="57181-164">안전한 링크는 들어오는 전자 메일에서 알려진 악성 하이퍼링크를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-164">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="57181-165">검사 된 Url은 Microsoft 표준 URL 접두사:을 사용 하 여 다시 쓰여집니다. `https://nam01.safelinks.protection.outlook.com`</span><span class="sxs-lookup"><span data-stu-id="57181-165">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="57181-166">링크를 다시 쓴 후에는 잠재적으로 악의적인 콘텐츠를 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-166">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="57181-167">안전한 링크에서 URL을 다시 작성 한 후에는 메시지가 전달 되거나 회신 되는 경우에도 URL이 다시 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-167">After Safe Links rewrites a URL, the URL remains rewritten, even if the message is forwarded or replied to.</span></span> <span data-ttu-id="57181-168">전달 되거나 회신 된 메시지에 추가 되는 추가 링크는 다시 쓰여지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-168">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span>

<span data-ttu-id="57181-169">전자 메일 메시지에 적용 되는 안전 링크 정책의 설정은 다음 목록에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-169">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="57181-170">**메시지에서 알 수 없는 잠재적 악성 url에 대 한 작업 선택**: 전자 메일 메시지에서 안전한 링크 검색을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-170">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="57181-171">권장 값은 **On**입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-171">The recommended value is **On**.</span></span> <span data-ttu-id="57181-172">이 설정을 켜면 다음과 같은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-172">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="57181-173">Windows의 Outlook (C2R)에서 안전한 링크 검색이 사용 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-173">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="57181-174">Url이 다시 작성 되 고 사용자가 메시지의 Url을 클릭할 때 안전한 링크 보호를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-174">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="57181-175">이 단추를 클릭 하면 알려진 악성 Url 목록과 ["다음 Url 차단" 목록](#block-the-following-urls-list-for-safe-links)에 대해 url을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-175">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="57181-176">유효한 신뢰도가 없는 Url은 백그라운드에서 비동기적으로 열.</span><span class="sxs-lookup"><span data-stu-id="57181-176">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="57181-177">**의심 스러운 링크 및 파일을 가리키는 링크에 대해 실시간 URL 검사 적용**: 다운로드 가능한 콘텐츠를 가리키는 전자 메일 메시지의 링크를 비롯 한 실시간 링크 검색을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-177">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="57181-178">권장 값은 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-178">The recommended value is enabled.</span></span>

  - <span data-ttu-id="57181-179">**메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다립니다**.</span><span class="sxs-lookup"><span data-stu-id="57181-179">**Wait for URL scanning to complete before delivering the message**:</span></span>

    - <span data-ttu-id="57181-180">Enabled: 검색이 완료 될 때까지 Url이 포함 된 메시지가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-180">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="57181-181">메시지는 Url이 안전한 것으로 확인 된 후에만 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-181">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="57181-182">권장 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-182">This is the recommended value.</span></span>
    - <span data-ttu-id="57181-183">사용 안 함: URL 검색을 완료할 수 없는 경우 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-183">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="57181-184">**조직 내에서 전송 되는 전자 메일 메시지에 안전한 링크 적용**: 같은 Exchange Online 조직 내에서 내부 보낸 사람과 내부 받는 사람 간에 전송 되는 메시지에 대해 안전한 링크 검색을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-184">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="57181-185">권장 값은 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-185">The recommended value is enabled.</span></span>

- <span data-ttu-id="57181-186">**사용자 클릭 추적 안 함**: 안전한 링크 저장을 사용 하거나 사용 하지 않도록 설정 전자 메일 메시지에서 클릭 한 url의 데이터를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-186">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="57181-187">권장 값은 사용자 클릭을 추적 하기 위해이 설정을 선택 하지 않은 채로 두는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-187">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="57181-188">URL 내부 보낸 사람과 내부 받는 사람 간에 전송 되는 전자 메일 메시지의 링크를 클릭 하는 것은 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-188">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="57181-189">**사용자가 원래 url로 클릭 하도록 허용 안 함**: 사용자가 [경고 페이지](#warning-pages-from-safe-links) 를 통해 원래 url을 클릭 하지 못하도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-189">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="57181-190">권장 값은 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-190">The recommend value is enabled.</span></span>

- <span data-ttu-id="57181-191">Url은 그대로 유지 **하 고 다음 url은 다시 쓰지**않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-191">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="57181-192">검색 하지 않아도 되는 안전한 Url의 사용자 지정 목록을 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-192">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="57181-193">이 목록은 각 안전한 링크 정책에 대해 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-193">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="57181-194">**다음 url에 다시 쓰지** 않음 목록에 대 한 자세한 내용은이 문서 뒷부분의 ["안전한 링크 정책에서 다음 url을 다시 쓰지 않음"](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-194">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="57181-195">안전한 링크 정책의 표준 및 엄격한 정책 설정에 대 한 권장 값에 대 한 자세한 내용은 [안전한 링크 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-195">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="57181-196">**받는 사람 필터**: 정책을 적용할 사람을 결정 하는 예외 및 받는 사람 조건을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-196">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="57181-197">다음 속성을 사용 하 여 조건 및 예외를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-197">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="57181-198">**받는 사람이 다음과 같음**</span><span class="sxs-lookup"><span data-stu-id="57181-198">**The recipient is**</span></span>
  - <span data-ttu-id="57181-199">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="57181-199">**The recipient domain is**</span></span>
  - <span data-ttu-id="57181-200">**받는 사람이 다음의 구성원임**</span><span class="sxs-lookup"><span data-stu-id="57181-200">**The recipient is a member of**</span></span>

  <span data-ttu-id="57181-201">조건 또는 예외는 한 번만 사용할 수 있지만 조건 또는 예외에 여러 값이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-201">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="57181-202">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="57181-202">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="57181-203">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="57181-203">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="57181-204">**우선 순위**: 여러 정책을 만드는 경우 적용 되는 순서를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-204">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="57181-205">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-205">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="57181-206">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57181-206">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="57181-207">전자 메일 메시지에서 안전한 링크가 작동 하는 방법</span><span class="sxs-lookup"><span data-stu-id="57181-207">How Safe Links works in email messages</span></span>

<span data-ttu-id="57181-208">다음은 전자 메일 메시지의 Url에 대 한 안전한 링크 보호 작동 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-208">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="57181-209">모든 전자 메일은 메시지가 받는 사람의 사서함으로 배달 되기 전에 IP (인터넷 프로토콜) 및 봉투 필터, 서명 기반 맬웨어 방지, 스팸 방지 및 맬웨어 방지 필터를 제공 하는 EOP를 통해 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-209">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="57181-210">사용자가 사서함에서 메시지를 열고 메시지의 URL을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-210">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="57181-211">안전한 링크는 웹 사이트를 열기 전에 즉시 URL을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-211">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="57181-212">URL이 **다음 Url 차단** 목록에 포함 되어 있는 경우 [차단 된 url 경고가](#blocked-url-warning) 열립니다.</span><span class="sxs-lookup"><span data-stu-id="57181-212">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="57181-213">URL이 악의적인 것으로 확인 된 웹 사이트를 가리키는 경우 [악의 있는 웹 사이트 경고](#malicious-website-warning) 페이지 (또는 다른 경고 페이지)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="57181-213">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="57181-214">URL이 다운로드 가능한 파일을 가리키며 해당 **링크에 대해 실시간 URL 검색 및 파일을 가리키는 링크** 를 사용자에 게 적용 되는 정책에서 사용 하도록 설정 된 경우 다운로드 가능한 파일이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-214">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="57181-215">URL이 안전한 것으로 확인 되 면 웹 사이트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="57181-215">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="57181-216">Microsoft 팀에 대 한 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="57181-216">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57181-217">3 월 2020 현재까지이 기능은 미리 보기 상태 이며 Microsoft 팀 기술 채택 프로그램의 구성원만 사용할 수 있습니다 (탭).</span><span class="sxs-lookup"><span data-stu-id="57181-217">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="57181-218">릴리스 일정에 대 한 자세한 내용은 [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57181-218">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="57181-219">안전한 링크 정책에서 Microsoft 팀에 대 한 안전한 링크 보호를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-219">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="57181-220">특히 **Microsoft 팀 내에서 알 수 없거나 악성 url에 대 한 작업 선택** 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-220">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="57181-221">권장 값은 **On**입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-221">The recommended value is **On**.</span></span>

<span data-ttu-id="57181-222">전자 메일 메시지의 링크에 적용 되는 안전한 링크 정책에서 팀의 링크에도 적용 되는 다음 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-222">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="57181-223">**의심 스러운 링크에 대 한 실시간 URL 검사 및 파일을 가리키는 링크를 적용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="57181-223">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="57181-224">**사용자 클릭 추적 안 함**</span><span class="sxs-lookup"><span data-stu-id="57181-224">**Do not track user clicks**</span></span>
- <span data-ttu-id="57181-225">**사용자가 원래 URL로 클릭 하도록 허용 안 함**</span><span class="sxs-lookup"><span data-stu-id="57181-225">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="57181-226">이러한 설정은 [전자 메일 메시지에 대 한 이전 안전한 링크 설정](#safe-links-settings-for-email-messages) 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-226">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="57181-227">Microsoft 팀에 대 한 안전한 링크 보호를 설정한 후에는 보호 된 사용자가 링크를 클릭할 때 알려진 악성 링크 목록 (팀의 Url)이 확인 됩니다 (클릭 시간 보호).</span><span class="sxs-lookup"><span data-stu-id="57181-227">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="57181-228">Url은 다시 작성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-228">URLs are not rewritten.</span></span> <span data-ttu-id="57181-229">링크가 악성 인 경우 사용자는 다음과 같은 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-229">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="57181-230">팀 대화, 그룹 채팅 또는 채널에서 링크를 클릭 한 경우 아래 스크린샷에 표시 된 경고 페이지가 기본 웹 브라우저에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-230">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="57181-231">고정 된 탭에서 링크를 클릭 한 경우에는 해당 탭 내의 팀 인터페이스에 경고 페이지가 표시 됩니다. 보안상의 이유로 링크를 웹 브라우저에서 여는 옵션은 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-231">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="57181-232">**사용자가 정책의 원래 url을 클릭** 하는 것을 허용 하지 않음 설정이 구성 된 방법에 따라 사용자는 원래 url (스크린샷에서는**계속 됨)** 을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-232">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="57181-233">사용자가 원래 url로 이동할 수 없도록 **하려면 사용자가 원래 url로 클릭 하도록 허용 안 함** 설정을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-233">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="57181-234">링크를 보낸 사용자가 팀 보호를 사용할 수 있는 안전한 링크 정책에 포함 되어 있지 않은 경우 사용자는 자신의 컴퓨터나 장치에서 원래 URL로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-234">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![악성 링크를 보고 하는 팀에 대 한 안전한 링크 페이지입니다.](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="57181-236">경고 페이지에서 **뒤로 이동** 단추를 클릭 하면 페이지가 닫히고 사용자가 닫을 수 있는 빈 페이지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-236">Clicking the **Go Back** button on the warning page will close the page (or might result in a blank page that users can close).</span></span> <span data-ttu-id="57181-237">그러나 원래 링크를 다시 클릭 하면 안전 링크를 통해 URL이 검사 되므로 경고 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="57181-237">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="57181-238">팀에서의 안전한 링크 작동 방식</span><span class="sxs-lookup"><span data-stu-id="57181-238">How Safe Links works in Teams</span></span>

<span data-ttu-id="57181-239">다음은 Microsoft 팀의 Url에 대 한 안전한 링크 보호 작동 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-239">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="57181-240">사용자가 팀 앱을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-240">A user starts the Teams app.</span></span>

2. <span data-ttu-id="57181-241">Microsoft 365에서는 사용자의 조직에 Office 365 ATP가 포함 되어 있고 사용자가 Microsoft 팀에 대 한 보호가 사용 하도록 설정 된 활성 안전한 링크 정책에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-241">Microsoft 365 verifies that the user's organization includes Office 365 ATP, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="57181-242">Url은 대화방, 그룹 채팅, 채널 및 탭에서 사용자를 클릭 하는 시점에 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-242">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="57181-243">Office 365 앱에 대 한 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="57181-243">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="57181-244">안전한 링크 보호 Office 365 앱은 전자 메일 메시지의 링크가 아니라 Office 문서의 링크를 확인 하지만 문서를 연 후 전자 메일 메시지에서 첨부 된 Office 문서의 링크를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-244">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="57181-245">Office 365 앱에 대 한 안전한 링크 보호는 다음과 같은 클라이언트 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-245">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="57181-246">Microsoft 365 앱 또는 Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="57181-246">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="57181-247">Windows, Mac 또는 웹 브라우저에서 현재 버전의 Word, Excel 및 PowerPoint입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-247">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="57181-248">IOS 또는 Android 장치에 대 한 Office 앱</span><span class="sxs-lookup"><span data-stu-id="57181-248">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="57181-249">Windows의 Visio</span><span class="sxs-lookup"><span data-stu-id="57181-249">Visio on Windows.</span></span>
  - <span data-ttu-id="57181-250">웹 브라우저의 OneNote</span><span class="sxs-lookup"><span data-stu-id="57181-250">OneNote in a web browser.</span></span>

- <span data-ttu-id="57181-251">Office 365 앱은 최신 인증을 사용 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-251">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="57181-252">자세한 내용은 [office 2013, office 2016 및 office 2019 클라이언트 앱에 대 한 최신 인증이 작동 하는 방법을](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57181-252">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span>

- <span data-ttu-id="57181-253">사용자가 회사 또는 학교 계정을 사용 하 여 로그인 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-253">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="57181-254">자세한 내용은 [Office에 로그인](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57181-254">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="57181-255">안전한 링크 정책이 아닌 안전한 링크에 대 한 전역 설정에서 Office 365 앱에 대 한 안전한 링크 보호를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-255">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="57181-256">그러나 Office 365 앱에 대 한 안전한 링크 보호를 적용 하려면 Office 문서를 열고 링크를 클릭 하는 사용자가 활성 안전한 링크 정책에 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-256">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="57181-257">Office 365 앱에 대해 다음과 같은 안전한 링크 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-257">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="57181-258">**Office 365 응용 프로그램**: 지원 되는 Office 365 앱에서 안전한 링크 검색을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-258">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="57181-259">기본값 및 권장 값이 **설정**되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-259">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="57181-260">**사용자가 안전한 링크를 클릭 하는 경우를 추적 하지 않음**: 안전한 링크 저장 사용 또는 사용 안 함 데스크톱 버전 Word, Excel, PowerPoint 및 Visio에서 클릭 한 url의 데이터를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-260">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="57181-261">권장 값은 **Off**이며, 사용자 클릭이 추적 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-261">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="57181-262">**사용자가 원본 url에 대 한 안전한 링크를 클릭**하는 것을 허용 하지 않음: 사용자가 데스크톱 버전 Word, Excel, PowerPoint 및 Visio의 원래 url로 [경고 페이지](#warning-pages-from-safe-links) 를 클릭 하는 것을 허용 하거나 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-262">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="57181-263">기본값 및 권장 값이 **설정**되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-263">The default and recommended value is **On**.</span></span>

<span data-ttu-id="57181-264">Office 365 앱에 대 한 안전한 링크 설정을 구성 하려면 [office 365 앱에 대 한 안전한 링크 보호 구성](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57181-264">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="57181-265">표준 및 엄격한 정책 설정에 대 한 권장 값에 대 한 자세한 내용은 [안전한 링크에 대 한 전역 설정을](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-265">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="57181-266">Office 365 앱에서 안전한 링크가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="57181-266">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="57181-267">다음은 Office 365 앱의 Url에 대 한 안전한 링크 보호 작동 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-267">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="57181-268">지원 되는 Office 365 앱은 이전 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-268">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="57181-269">사용자는 Microsoft 365 앱 또는 Microsoft 365 Business Premium이 포함 된 조직의 회사 또는 학교 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-269">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="57181-270">사용자가 지원 되는 Office 앱에서 Office 문서 링크를 열고 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-270">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="57181-271">안전한 링크는 대상 웹 사이트를 열기 전에 즉시 URL을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-271">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="57181-272">안전한 링크 검색을 건너뛰는 목록에 URL이 포함 되어 있는 경우 ( **다음 url 목록 차단** ) [차단 된 url 경고](#blocked-url-warning) 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="57181-272">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="57181-273">URL이 악의적인 것으로 확인 된 웹 사이트를 가리키는 경우 [악의 있는 웹 사이트 경고](#malicious-website-warning) 페이지 (또는 다른 경고 페이지)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="57181-273">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="57181-274">URL이 다운로드 가능한 파일을 가리키고 사용자에 게 적용 되는 안전 링크 정책이 다운로드 가능한 콘텐츠에 대 한 링크를 검색 하도록 구성 된 경우 (**의심 스러운 링크 및 파일을 가리키는 링크에 대해 실시간 URL 검색 적용**) 다운로드 가능한 파일이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-274">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="57181-275">URL이 안전한 것으로 간주 되 면 사용자는 웹 사이트로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-275">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="57181-276">안전한 링크 검색을 완료할 수 없는 경우 안전한 링크 보호가 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-276">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="57181-277">Office 데스크톱 클라이언트에서는 대상 웹 사이트로 진행 하기 전에 사용자에 게 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-277">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="57181-278">각 세션이 시작 되는 동안 사용자가 Office에 대 한 안전한 링크를 사용 하도록 설정 되어 있는지 확인 하는 데 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-278">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="57181-279">안전한 링크에 대 한 "다음 Url 차단" 목록</span><span class="sxs-lookup"><span data-stu-id="57181-279">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="57181-280">**다음 Url 차단** 목록에서는 다음 위치에 있는 안전한 링크 검색에서 항상 차단 되는 링크를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-280">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="57181-281">전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="57181-281">Email messages.</span></span>
- <span data-ttu-id="57181-282">Windows 및 Mac의 Office 365 앱에 있는 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-282">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="57181-283">IOS 및 Android 용 Office의 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-283">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="57181-284">활성 안전한 링크 정책의 사용자가 지원 되는 앱에서 차단 된 링크를 클릭 하면 [차단 된 URL 경고](#blocked-url-warning) 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-284">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="57181-285">안전한 링크에 대 한 전역 설정에서 Url 목록을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-285">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="57181-286">자세한 내용은 Configure the ["다음 Url 차단" 목록을](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57181-286">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="57181-287">**참고**:</span><span class="sxs-lookup"><span data-stu-id="57181-287">**Notes**:</span></span>

- <span data-ttu-id="57181-288">모든 범위에서 차단 되는 Url의 진정한 범용 목록은 [테 넌 트 허용/차단 목록에서 Url 관리](tenant-allow-block-list.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-288">For a truly universal list of URLs that are blocked everywhere, see [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="57181-289">크기</span><span class="sxs-lookup"><span data-stu-id="57181-289">Limits:</span></span>
  - <span data-ttu-id="57181-290">최대 항목 수는 500입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-290">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="57181-291">항목의 최대 길이는 128 자입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-291">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="57181-292">모든 항목은 1만 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-292">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="57181-293">URL의 끝에 슬래시 ()를 포함 하지 마십시오 `/` .</span><span class="sxs-lookup"><span data-stu-id="57181-293">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="57181-294">예를 들어 `https://www.contoso.com` ,를 사용 `https://www.contoso.com/` 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-294">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="57181-295">도메인 전용-URL (예: `contoso.com` 또는 `tailspintoys.com` )은 도메인을 포함 하는 모든 url을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-295">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="57181-296">전체 도메인을 차단 하지 않고 하위 도메인을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-296">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="57181-297">예를 `toys.contoso.com*` 들어 하위 도메인이 포함 된 모든 url을 차단 하지만 전체 도메인을 포함 하는 url은 차단 되지 않습니다 `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="57181-297">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="57181-298">URL 항목당 최대 3 개의 와일드 카드 ()를 포함할 수 있습니다 `*` .</span><span class="sxs-lookup"><span data-stu-id="57181-298">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="57181-299">"다음 Url 차단" 목록의 항목 구문</span><span class="sxs-lookup"><span data-stu-id="57181-299">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="57181-300">입력할 수 있는 값과 결과에 대 한 예는 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-300">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="57181-301">값</span><span class="sxs-lookup"><span data-stu-id="57181-301">Value</span></span>|<span data-ttu-id="57181-302">결과</span><span class="sxs-lookup"><span data-stu-id="57181-302">Result</span></span>|
|---|---|
|`contoso.com` <br/> <span data-ttu-id="57181-303">또는</span><span class="sxs-lookup"><span data-stu-id="57181-303">or</span></span> <br/> `*contoso.com*`|<span data-ttu-id="57181-304">Domain, 하위 도메인 및 경로를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-304">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="57181-305">예를 들어 `https://www.contoso.com` `https://sub.contoso.com` and `https://contoso.com/abc` 는 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-305">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="57181-306">블록 `https://contoso.com/a` 이지만 추가 하위 경로는 `https://contoso.com/a/b` 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="57181-306">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="57181-307">블록과 `https://contoso.com/a` 추가 하위 경로를 선택 `https://contoso.com/a/b` 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-307">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="57181-308">하위 도메인 ( `toys` 이 예에서)을 차단 하지만 클릭이 다른 도메인 url (예: `https://contoso.com` 또는 `https://home.contoso.com` )을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-308">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="57181-309">안전한 링크 정책의 "다음 Url을 다시 쓰지 않음" 목록</span><span class="sxs-lookup"><span data-stu-id="57181-309">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="57181-310">조직에서 안전한 링크 정책을 사용 하는 경우 타사 피싱 테스트 **에서는 다음 url** 목록만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-310">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="57181-311">각 안전 링크 정책에는 안전한 링크 검색을 통해 다시 쓰지 않는 Url을 지정 하는 데 사용할 수 있는 **다음 url** 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-311">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="57181-312">즉,이 목록을 사용 하면 정책에 포함 된 사용자가 안전한 링크에 의해 차단 되는 지정 된 Url에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-312">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="57181-313">서로 다른 안전한 링크 정책에서 서로 다른 목록을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-313">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="57181-314">사용자에 게 첫 번째 (우선 순위가 가장 높은) 정책이 적용 된 후에는 정책 처리가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-314">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="57181-315">따라서 여러 활성 안전한 링크 정책에 포함 된 사용자에 게는 **다음 url 목록을 다시 쓰지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-315">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="57181-316">새 또는 기존 안전한 링크 정책에서 목록에 항목을 추가 하려면 [안전한 링크 정책 만들기](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 또는 [안전한 링크 정책 수정을](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-316">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="57181-317">**참고**:</span><span class="sxs-lookup"><span data-stu-id="57181-317">**Notes**:</span></span>

- <span data-ttu-id="57181-318">다음 클라이언트는 안전한 링크 정책에서 **다음 url 목록을 다시 쓰지 않습니다** .를 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-318">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="57181-319">정책에 포함 된 사용자는 다음 클라이언트에서 안전한 링크 검색 결과에 따라 Url에 액세스 하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-319">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="57181-320">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57181-320">Microsoft Teams</span></span>
  - <span data-ttu-id="57181-321">Office web apps</span><span class="sxs-lookup"><span data-stu-id="57181-321">Office web apps</span></span>

  <span data-ttu-id="57181-322">모든 위치에서 허용 되는 진정한 범용 Url 목록은 [테 넌 트 허용/차단 목록에서 Url 관리](tenant-allow-block-list.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57181-322">For a truly universal list of URLs that are allowed everywhere, see [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="57181-323">일반적으로 사용 되는 내부 Url을 목록에 추가 하 여 사용자 환경을 개선 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-323">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="57181-324">예를 들어 비즈니스용 Skype 또는 SharePoint와 같은 온-프레미스 서비스를 사용 하는 경우 해당 Url을 추가 하 여 검색에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-324">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="57181-325">안전한 링크 정책에서 **다음 url 항목을 이미 다시 작성 하지** 않은 경우에는 목록을 검토 하 고 필요에 따라 와일드 카드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-325">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="57181-326">예를 들어 목록에 항목이 있고 `https://contoso.com/a` 나중에 하위 경로를 포함 하기로 결정 하는 경우를 예로 들 수 있습니다 `https://contoso.com/a/b` .</span><span class="sxs-lookup"><span data-stu-id="57181-326">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="57181-327">새 항목을 추가 하는 대신 기존 항목에 와일드 카드를 추가 하 여 해당 항목이 되도록 `https://contoso.com/a/*` 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-327">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="57181-328">URL 항목당 최대 3 개의 와일드 카드 ()를 포함할 수 있습니다 `*` .</span><span class="sxs-lookup"><span data-stu-id="57181-328">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="57181-329">와일드 카드에 접두사 또는 하위 도메인이 명시적으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-329">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="57181-330">예를 들어 항목은 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` 지정 된 도메인의 하위 도메인과 경로를 방문 하도록 허용 하므로와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="57181-330">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="57181-331">"다음 Url을 다시 쓰지 않음" 목록의 항목 구문</span><span class="sxs-lookup"><span data-stu-id="57181-331">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="57181-332">입력할 수 있는 값과 결과에 대 한 예는 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-332">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="57181-333">값</span><span class="sxs-lookup"><span data-stu-id="57181-333">Value</span></span>|<span data-ttu-id="57181-334">결과</span><span class="sxs-lookup"><span data-stu-id="57181-334">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="57181-335">하위 `https://contoso.com` 도메인 이나 경로가 아닌 액세스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-335">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="57181-336">도메인, 하위 도메인 및 경로 (예:,, 또는)에 대 한 액세스를 허용 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` 합니다.</span><span class="sxs-lookup"><span data-stu-id="57181-336">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <br/><br/> <span data-ttu-id="57181-337">이 항목은 `*contoso.com*` 다음과 같이 잠재적으로 사기성 사이트를 허용 하지 않기 때문에 보다 안전 합니다. `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="57181-337">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="57181-338">경로 액세스를 허용 `https://contoso.com/a` 하지만 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="57181-338">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="57181-339">같은 액세스 및 하위 경로를 사용할 수 있습니다. `https://contoso.com/a``https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="57181-339">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="57181-340">안전한 링크의 경고 페이지</span><span class="sxs-lookup"><span data-stu-id="57181-340">Warning pages from Safe Links</span></span>

<span data-ttu-id="57181-341">이 섹션에는 URL을 클릭 했을 때 안전한 링크 보호에 의해 트리거되는 다양 한 경고 페이지 예제가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-341">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="57181-342">여러 개의 경고 페이지가 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-342">Note that several warning pages have been updated.</span></span> <span data-ttu-id="57181-343">업데이트 된 페이지가 표시 되지 않으면 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="57181-343">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="57181-344">업데이트 된 페이지에는 지정 된 경고 및 권장 사항에도 불구 하 고 사이트를 계속 진행 하는 기능 및 새로운 색 구성표가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-344">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="57181-345">검색 진행 중 알림</span><span class="sxs-lookup"><span data-stu-id="57181-345">Scan in progress notification</span></span>

<span data-ttu-id="57181-346">클릭 한 URL을 안전한 링크에서 검색 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-346">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="57181-347">잠시 기다린 후에 링크를 다시 시도해 야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-347">You might need to wait a few moments before trying the link again.</span></span>

!["링크를 검색 하 고 있습니다." 알림](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="57181-349">원래 알림 페이지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-349">The original notification page looked like this:</span></span>

![원본 "링크를 검색 하 고 있습니다." 알림](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="57181-351">의심 스러운 메시지 경고</span><span class="sxs-lookup"><span data-stu-id="57181-351">Suspicious message warning</span></span>

<span data-ttu-id="57181-352">클릭 한 URL이 다른 의심 스러운 메시지와 비슷한 전자 메일 메시지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-352">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="57181-353">사이트를 진행 하기 전에 전자 메일 메시지를 두 번 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-353">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["의심 스러운 메시지에서 링크를 클릭 했습니다." 경고](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="57181-355">피싱 시도 경고</span><span class="sxs-lookup"><span data-stu-id="57181-355">Phishing attempt warning</span></span>

<span data-ttu-id="57181-356">클릭 한 URL이 피싱 공격으로 식별 된 전자 메일 메시지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-356">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="57181-357">따라서 전자 메일 메시지의 모든 Url이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-357">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="57181-358">해당 사이트로 이동 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-358">We recommend that you do not proceed to the site.</span></span>

!["피싱 메시지에서 링크 클릭 됨" 경고](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="57181-360">악의적인 웹 사이트 경고</span><span class="sxs-lookup"><span data-stu-id="57181-360">Malicious website warning</span></span>

<span data-ttu-id="57181-361">클릭 한 URL이 악성으로 식별 된 사이트를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="57181-361">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="57181-362">해당 사이트로 이동 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-362">We recommend that you do not proceed to the site.</span></span>

!["이 웹 사이트가 악성으로 분류 되어 있습니다." 경고](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="57181-364">원래 경고 페이지는 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-364">The original warning page looked like this:</span></span>

![원본 "이 웹 사이트가 악의적인 것으로 분류 됨" 경고](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="57181-366">차단 된 URL 경고</span><span class="sxs-lookup"><span data-stu-id="57181-366">Blocked URL warning</span></span>

<span data-ttu-id="57181-367">조직의 관리자가 클릭 한 URL을 수동으로 차단 했습니다 (안전한 링크에 대 한 전역 설정에서 **다음 url 목록 차단** ).</span><span class="sxs-lookup"><span data-stu-id="57181-367">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="57181-368">링크가 수동으로 차단 되었기 때문에 안전한 링크에서 검색 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-368">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="57181-369">관리자가 특정 Url을 수동으로 차단 하는 이유에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-369">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="57181-370">사이트를 차단 하지 않을 것으로 생각 되 면 관리자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="57181-370">If you think the site should not be blocked, contact your admin.</span></span>

!["이 웹 사이트가 관리자에 의해 차단 되었습니다." 경고](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="57181-372">원래 경고 페이지는 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-372">The original warning page looked like this:</span></span>

![원본 "이 웹 사이트가 조직의 URL 정책에 따라 차단 되었습니다." 경고](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="57181-374">오류 경고</span><span class="sxs-lookup"><span data-stu-id="57181-374">Error warning</span></span>

<span data-ttu-id="57181-375">오류가 발생 하 여 URL을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57181-375">Some kind of error has occurred, and the URL can't be opened.</span></span>

!["액세스 하려는 페이지를 로드할 수 없습니다." 경고](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="57181-377">원래 경고 페이지는 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57181-377">The original warning page looked like this:</span></span>

![원본 "이 웹 페이지를 로드할 수 없습니다." 경고](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
