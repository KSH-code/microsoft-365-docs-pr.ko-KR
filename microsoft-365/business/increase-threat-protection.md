---
title: 비즈니스용 보안 기능의 Microsoft 365 보호 강화
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 피싱, Office 365 및 기타 위협으로부터 중요한 데이터를 보호하고 보호할 수 있는 Microsoft Defender를 설정하십시오.
ms.openlocfilehash: a995063cef6fdc42ad62079d49d58edc9d07b52c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924322"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="4a6df-103">위협 방지 강화</span><span class="sxs-lookup"><span data-stu-id="4a6df-103">Increase threat protection</span></span>

<span data-ttu-id="4a6df-104">이 문서는 피싱, 맬웨어 및 기타 위협으로부터 보호하기 위해 Microsoft 365 구독의 보호를 강화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="4a6df-105">이러한 권장 사항은 법률 사무소 및 의료 기관과 같이 보안에 대한 필요성이 증가하는 조직에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-105">These recommendations are appropriate for organizations with an increased need for security, like law offices and health care clinics.</span></span>

<span data-ttu-id="4a6df-106">시작하기 전에 보안 점수를 Office 365 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="4a6df-107">Office 365 보안 점수는 정기적인 활동 및 보안 설정에 따라 조직의 보안을 분석하고 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-107">Office 365 Secure Score analyzes your organization's security based on your regular activities and security settings, and assigns a score.</span></span> <span data-ttu-id="4a6df-108">먼저 현재 점수를 기록해 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="4a6df-109">점수를 높이기 위해 이 문서에서 권장하는 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-109">To increase your score, complete the actions recommended in this article.</span></span> <span data-ttu-id="4a6df-110">목표는 최대 점수를 달성하는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호할 기회를 인식하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-110">The goal isn't to achieve the maximum score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="4a6df-111">자세한 내용은 Microsoft 보안 점수를 [참조하세요.](../security/defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="4a6df-111">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="4a6df-112">메일의 맬웨어에 대한 보호 수준 높이기</span><span class="sxs-lookup"><span data-stu-id="4a6df-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="4a6df-113">사용자 Office 365 Microsoft 365 맬웨어에 대한 보호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-113">Your Office 365 or Microsoft 365 environment includes protection against malware.</span></span> <span data-ttu-id="4a6df-114">맬웨어에 일반적으로 사용되는 파일 형식의 첨부 파일을 차단하여 이 보호를 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-114">You can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="4a6df-115">전자 메일에서 맬웨어 보호를 강화하는 방법:</span><span class="sxs-lookup"><span data-stu-id="4a6df-115">To increase malware protection in email:</span></span>

1. <span data-ttu-id="4a6df-116">으로 [https://protection.office.com](https://protection.office.com) 이동하여 관리자 계정 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-116">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="4a6df-117">보안 및 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 정책 &amp; 맬웨어 방지   \> **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-117">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="4a6df-118">기본 정책을 두 번 클릭하여 이 회사 전체 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-118">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="4a6df-119">**설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-119">Select **Settings**.</span></span>

5. <span data-ttu-id="4a6df-120">일반 **첨부 파일 형식 필터에서** 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-120">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="4a6df-121">차단된 파일 형식은 이 컨트롤 바로 아래에 있는 창에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-121">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="4a6df-122">다음 파일 형식을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-122">Make sure that you add these file types:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="4a6df-123">필요한 경우 나중에 파일 형식을 추가하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-123">If necessary, you can add or delete file types later.</span></span>

6. <span data-ttu-id="4a6df-124">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-124">Select **Save.**</span></span>

<span data-ttu-id="4a6df-125">자세한 내용은 [EOP의 맬웨어 방지 보호를 참조하세요.](../security/office-365-security/anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4a6df-125">For more information, see [Anti-malware protection in EOP](../security/office-365-security/anti-malware-protection.md).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="4a6df-126">랜섬웨어로부터 보호</span><span class="sxs-lookup"><span data-stu-id="4a6df-126">Protect against ransomware</span></span>

<span data-ttu-id="4a6df-127">랜섬웨어는 파일을 암호화하거나 컴퓨터 화면을 잠가 데이터에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="4a6df-128">그런 다음 데이터에 대한 액세스 대가로 일반적으로 가상화 형식의 "금전"을 요청하여 피해자로부터 돈을 유출하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-128">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="4a6df-129">랜섬웨어로부터 보호하기 위해 하나 이상의 메일 흐름 규칙을 만들어 랜섬웨어에 일반적으로 사용되는 파일 확장명을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-129">To protect against ransomware, create one or more mail flow rules to block file extensions that are commonly used for ransomware.</span></span> <span data-ttu-id="4a6df-130">메일 단계에서 맬웨어에 대한 보호 수준을 [높이기](#raise-the-level-of-protection-against-malware-in-mail) 위해 이러한 규칙을 추가했습니다. 전자 메일로 이러한 첨부 파일을 받는 사용자에게 경고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-130">(You added these rules in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step.) You can also warn users who receive these attachments in email.</span></span>

<span data-ttu-id="4a6df-131">이전 단계에서 차단한 파일 외에도 매크로가 포함된 첨부 파일을 열기 전에 사용자에게 경고하는 Office 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-131">In addition to the files that you blocked in the previous step, it's a good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="4a6df-132">매크로 내에서 랜섬웨어를 숨길 수 있으므로 모르는 사용자로부터 이러한 파일을 열지 못하게 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-132">Ransomware can be hidden inside macros, so warn users not to open these files from people they don't know.</span></span>

<span data-ttu-id="4a6df-133">메일 전송 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-133">To create a mail transport rule:</span></span>

1. <span data-ttu-id="4a6df-134">의 관리 센터로 이동하여 관리 센터 <https://admin.microsoft.com>  \> Exchange.</span><span class="sxs-lookup"><span data-stu-id="4a6df-134">Go to the admin center at <https://admin.microsoft.com>, and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="4a6df-135">메일 **흐름 범주에서** 규칙을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-135">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="4a6df-136">**+** 를 선택한 다음 새 규칙 **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-136">Select **+**, and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="4a6df-137">전체 **옵션 집합을** 확인하려면 대화 상자 아래쪽에서 다른 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-137">Select **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="4a6df-138">규칙에 대한 다음 표의 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-138">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="4a6df-139">나머지 설정은 변경하지 않는 한 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-139">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="4a6df-140">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-140">Select **Save**.</span></span>

|<span data-ttu-id="4a6df-141">설정</span><span class="sxs-lookup"><span data-stu-id="4a6df-141">Setting</span></span>|<span data-ttu-id="4a6df-142">파일 첨부 파일을 열기 전에 Office 경고</span><span class="sxs-lookup"><span data-stu-id="4a6df-142">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="4a6df-143">이름</span><span class="sxs-lookup"><span data-stu-id="4a6df-143">Name</span></span>|<span data-ttu-id="4a6df-144">랜섬웨어 방지 규칙: 사용자에게 경고</span><span class="sxs-lookup"><span data-stu-id="4a6df-144">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="4a6df-145">이 경우 이 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-145">Apply this rule if .</span></span> <span data-ttu-id="4a6df-146">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-146">.</span></span> <span data-ttu-id="4a6df-147">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-147">.</span></span>|<span data-ttu-id="4a6df-148">모든 첨부 파일 .</span><span class="sxs-lookup"><span data-stu-id="4a6df-148">Any attachment .</span></span> <span data-ttu-id="4a6df-149">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-149">.</span></span> <span data-ttu-id="4a6df-150">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-150">.</span></span> <span data-ttu-id="4a6df-151">파일 확장명은 을 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-151">file extension matches .</span></span> <span data-ttu-id="4a6df-152">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-152">.</span></span> <span data-ttu-id="4a6df-153">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-153">.</span></span>|
|<span data-ttu-id="4a6df-154">단어 또는 구 지정</span><span class="sxs-lookup"><span data-stu-id="4a6df-154">Specify words or phrases</span></span>|<span data-ttu-id="4a6df-155">다음 파일 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-155">Add these file types:</span></span>  <br/> <span data-ttu-id="4a6df-156">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span><span class="sxs-lookup"><span data-stu-id="4a6df-156">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>|
|<span data-ttu-id="4a6df-157">다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-157">Do the following .</span></span> <span data-ttu-id="4a6df-158">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-158">.</span></span> <span data-ttu-id="4a6df-159">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-159">.</span></span>|<span data-ttu-id="4a6df-160">받는 사람에게 메시지로 알림</span><span class="sxs-lookup"><span data-stu-id="4a6df-160">Notify the recipient with a message</span></span>|
|<span data-ttu-id="4a6df-161">메시지 텍스트 제공</span><span class="sxs-lookup"><span data-stu-id="4a6df-161">Provide message text</span></span>|<span data-ttu-id="4a6df-162">악성 코드가 포함된 매크로가 포함되어 있을 수 있기 때문에 모르는 사용자로부터 이러한 형식의 파일을 열지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-162">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="4a6df-163">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a6df-163">For more information, see:</span></span>

- [<span data-ttu-id="4a6df-164">랜섬웨어: 위험을 줄이는 방법</span><span class="sxs-lookup"><span data-stu-id="4a6df-164">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="4a6df-165">사용자 OneDrive</span><span class="sxs-lookup"><span data-stu-id="4a6df-165">Restore your OneDrive</span></span>](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="4a6df-166">전자 메일에 대한 자동 전달 중지</span><span class="sxs-lookup"><span data-stu-id="4a6df-166">Stop auto-forwarding for email</span></span>

<span data-ttu-id="4a6df-167">사용자의 사서함에 액세스할 수 있는 해커는 사서함이 자동으로 전자 메일을 전달하도록 설정하여 메일을 도용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-167">Hackers who gain access to a user's mailbox can steal mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="4a6df-168">이는 사용자의 인식 없이도 발생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-168">This can happen even without the user's awareness.</span></span> <span data-ttu-id="4a6df-169">이러한 문제를 방지할 수 있도록 메일 흐름 규칙을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-169">To prevent this from happening, configure a mail flow rule.</span></span>

<span data-ttu-id="4a6df-170">메일 전송 규칙을 만들 수 [](../business-video/stop-email-auto-forward.md) 있는 경우 이 짧은 비디오를 시청하거나 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4a6df-170">To create a mail transport rule, either watch [this short video](../business-video/stop-email-auto-forward.md) or follow these steps:</span></span>

1. <span data-ttu-id="4a6df-171">Microsoft 365 관리 센터에서 관리 센터를  \> **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-171">In the Microsoft 365 admin center, select **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="4a6df-172">메일 **흐름 범주에서** 규칙을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-172">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="4a6df-173">**+** 를 선택한 다음 새 규칙 **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-173">Select **+**, and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="4a6df-174">모든 옵션을 확인하려면 대화 **상자** 아래쪽에서 다른 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-174">To see all the options, select **More options** at the bottom of the dialog box.</span></span>

5. <span data-ttu-id="4a6df-175">다음 표의 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-175">Apply the settings in the following table.</span></span> <span data-ttu-id="4a6df-176">나머지 설정은 변경하지 않는 한 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-176">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="4a6df-177">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-177">Select **Save**.</span></span>

|<span data-ttu-id="4a6df-178">설정</span><span class="sxs-lookup"><span data-stu-id="4a6df-178">Setting</span></span>|<span data-ttu-id="4a6df-179">파일 첨부 파일을 열기 전에 Office 경고</span><span class="sxs-lookup"><span data-stu-id="4a6df-179">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="4a6df-180">이름</span><span class="sxs-lookup"><span data-stu-id="4a6df-180">Name</span></span>|<span data-ttu-id="4a6df-181">외부 도메인으로 전자 메일 자동 전달 방지</span><span class="sxs-lookup"><span data-stu-id="4a6df-181">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="4a6df-182">다음의 경우 이 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-182">Apply this rule if ...</span></span>|<span data-ttu-id="4a6df-183">보낸 사람 입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-183">The sender .</span></span> <span data-ttu-id="4a6df-184">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-184">.</span></span> <span data-ttu-id="4a6df-185">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-185">.</span></span> <span data-ttu-id="4a6df-186">은 외부/내부입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-186">is external/internal .</span></span> <span data-ttu-id="4a6df-187">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-187">.</span></span> <span data-ttu-id="4a6df-188">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-188">.</span></span> <span data-ttu-id="4a6df-189">조직 내부</span><span class="sxs-lookup"><span data-stu-id="4a6df-189">Inside the organization</span></span>|
|<span data-ttu-id="4a6df-190">조건 추가</span><span class="sxs-lookup"><span data-stu-id="4a6df-190">Add condition</span></span>|<span data-ttu-id="4a6df-191">메시지 속성 입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-191">The message properties .</span></span> <span data-ttu-id="4a6df-192">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-192">.</span></span> <span data-ttu-id="4a6df-193">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-193">.</span></span> <span data-ttu-id="4a6df-194">메시지 유형 을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-194">include the message type .</span></span> <span data-ttu-id="4a6df-195">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-195">.</span></span> <span data-ttu-id="4a6df-196">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-196">.</span></span> <span data-ttu-id="4a6df-197">자동 전달</span><span class="sxs-lookup"><span data-stu-id="4a6df-197">Auto-forward</span></span>|
|<span data-ttu-id="4a6df-198">다음 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-198">Do the following ...</span></span>|<span data-ttu-id="4a6df-199">메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-199">Block the message .</span></span> <span data-ttu-id="4a6df-200">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-200">.</span></span> <span data-ttu-id="4a6df-201">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-201">.</span></span> <span data-ttu-id="4a6df-202">메시지를 거부하고 설명을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-202">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="4a6df-203">메시지 텍스트 제공</span><span class="sxs-lookup"><span data-stu-id="4a6df-203">Provide message text</span></span>|<span data-ttu-id="4a6df-204">보안상의 이유로 이 조직 외부에서 전자 메일을 자동 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-204">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="4a6df-205">피싱 공격으로부터 전자 메일 보호</span><span class="sxs-lookup"><span data-stu-id="4a6df-205">Protect your email from phishing attacks</span></span>

<span data-ttu-id="4a6df-206">Office 365 또는 Microsoft 365 사용자 지정 도메인을 하나 이상 구성한 경우 대상 피싱 방지 보호를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-206">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="4a6df-207">Microsoft Defender for Office 365 피싱 방지 보호는 악의적인 가장 기반 피싱 공격 및 기타 피싱 공격으로부터 조직을 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-207">Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="4a6df-208">사용자 지정 도메인을 구성하지 않은 경우 이 작업을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-208">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="4a6df-209">가장 중요한 사용자와 사용자 지정 도메인을 보호하는 정책을 만들어 이 보호를 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-209">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="4a6df-210">Microsoft Defender에서 피싱 방지 정책을 Office 365 이 짧은 교육 [](../business-video/setup-anti-phishing.md)비디오를 시청하거나 다음 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="4a6df-210">To create an anti-phishing policy in Microsoft Defender for Office 365, watch  [this short training video](../business-video/setup-anti-phishing.md), or complete the following steps:</span></span>

1. <span data-ttu-id="4a6df-211">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-211">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="4a6df-212">보안 및 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 &amp; 정책을 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="4a6df-212">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="4a6df-213">정책 **페이지에서** 피싱 **방지 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-213">On the **Policy** page, choose **Anti-phishing**.</span></span>

4. <span data-ttu-id="4a6df-214">피싱 **방지 페이지에서** + **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-214">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="4a6df-215">피싱 방지 정책을 정의하는 단계를 안내하는 마법사가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-215">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="4a6df-216">다음 표에서 권장되는 정책의 이름, 설명 및 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-216">Specify the name, description, and settings for your policy as recommended in the following table.</span></span> <span data-ttu-id="4a6df-217">자세한 내용은 Microsoft [Defender에서](../security/office-365-security/set-up-anti-phishing-policies.md)피싱 방지 정책에 대해 자세히 Office 365 옵션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a6df-217">For more details, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

6. <span data-ttu-id="4a6df-218">설정을 검토한 후 이 정책  만들기 또는 **저장을** 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-218">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="4a6df-219">설정 또는 옵션</span><span class="sxs-lookup"><span data-stu-id="4a6df-219">Setting or option</span></span>|<span data-ttu-id="4a6df-220">권장 설정</span><span class="sxs-lookup"><span data-stu-id="4a6df-220">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="4a6df-221">이름</span><span class="sxs-lookup"><span data-stu-id="4a6df-221">Name</span></span>|<span data-ttu-id="4a6df-222">도메인 및 가장 중요한 캠페인 직원</span><span class="sxs-lookup"><span data-stu-id="4a6df-222">Domain and most valuable campaign staff</span></span>|
|<span data-ttu-id="4a6df-223">설명</span><span class="sxs-lookup"><span data-stu-id="4a6df-223">Description</span></span>|<span data-ttu-id="4a6df-224">가장 중요한 직원과 도메인이 가장되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-224">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="4a6df-225">보호할 사용자를 추가</span><span class="sxs-lookup"><span data-stu-id="4a6df-225">Add users to protect</span></span>|<span data-ttu-id="4a6df-226">+ **조건 추가를 선택합니다. 받는 사람은 입니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-226">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="4a6df-227">사용자 이름을 입력하거나 후보, 캠페인 관리자 및 기타 중요한 직원 구성원의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-227">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="4a6df-228">가장으로부터 보호할 내부 및 외부 주소를 최대 20개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-228">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="4a6df-229">보호할 도메인을 추가</span><span class="sxs-lookup"><span data-stu-id="4a6df-229">Add domains to protect</span></span>|<span data-ttu-id="4a6df-230">+ **조건 추가를 선택하고 받는 사람 도메인은 입니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-230">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="4a6df-231">사용자 지정 도메인을 정의한 경우 Microsoft 365 사용자 지정 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-231">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="4a6df-232">두 개 이상의 도메인을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-232">You can enter more than one domain.</span></span>|
|<span data-ttu-id="4a6df-233">작업 선택</span><span class="sxs-lookup"><span data-stu-id="4a6df-233">Choose actions</span></span>|<span data-ttu-id="4a6df-234">가장된 사용자가 전자 메일을 보낸 경우: **메시지를** 다른 전자 메일 주소로 리디렉션을 선택한 다음 보안 관리자의 전자 메일 주소를 입력합니다. 예를 들어 *Alice <span> <span> @contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="4a6df-234">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <span data-ttu-id="4a6df-235">가장된 도메인에서 전자 메일을 보내는 경우: **격리 메시지** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-235">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="4a6df-236">사서함 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="4a6df-236">Mailbox intelligence</span></span>|<span data-ttu-id="4a6df-237">새 피싱 방지 정책을 만들 때 기본적으로 사서함 인텔리전스가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-237">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="4a6df-238">최상의 결과를 위해 해당 설정을 **켜짐** 에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-238">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="4a6df-239">신뢰할 수 있는 발신자와 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="4a6df-239">Add trusted senders and domains</span></span>|<span data-ttu-id="4a6df-240">여기에서 자체 도메인 또는 기타 신뢰할 수 있는 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-240">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="4a6df-241">적용 대상</span><span class="sxs-lookup"><span data-stu-id="4a6df-241">Applied to</span></span>|<span data-ttu-id="4a6df-242">**받는 사람의 도메인이 다음과 같음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-242">Select **The recipient domain is**.</span></span> <span data-ttu-id="4a6df-243">**이러한 항목 모두** 아래에서 **선택** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-243">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="4a6df-244">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-244">Select **+ Add**.</span></span> <span data-ttu-id="4a6df-245">도메인 이름 옆의 확인란(예: *contoso)을 선택합니다. <span> <span> 목록에서 com* 을 선택하고 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-245">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="4a6df-246">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-246">Select **Done**.</span></span>|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a><span data-ttu-id="4a6df-247">안전한 첨부 파일을 통해 악의적인 첨부 파일 및 파일로부터 보호</span><span class="sxs-lookup"><span data-stu-id="4a6df-247">Protect against malicious attachments and files with Safe Attachments</span></span>

<span data-ttu-id="4a6df-248">문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-248">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="4a6df-249">전자 메일 메시지를 확인하여 첨부 파일이 안전한지 악성인지를 항상 쉽게 알 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-249">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="4a6df-250">Microsoft Defender for Office 365 안전한 첨부 파일 보호가 포함되어 있지만 이 보호는 기본적으로 켜져 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-250">Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="4a6df-251">이 보호를 사용하 여 시작 하는 새 규칙을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-251">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="4a6df-252">이 보호는 SharePoint, OneDrive 및 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4a6df-252">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="4a6df-253">안전한 첨부 파일 정책을 만들거나 [](../business-video/safe-attachments.md)이 짧은 비디오를 시청하거나 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-253">To create an Safe Attachment policy, either watch [this short video](../business-video/safe-attachments.md), or complete the following steps:</span></span>

1. <span data-ttu-id="4a6df-254">로 [https://protection.office.com](https://protection.office.com) 이동하여 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-254">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="4a6df-255">보안 및 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 &amp; 정책을 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="4a6df-255">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="4a6df-256">정책 페이지에서 안전한 첨부 **파일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-256">On the Policy page, choose **Safe Attachments**.</span></span>

4. <span data-ttu-id="4a6df-257">안전한 첨부 파일 페이지에서 SharePoint, OneDrive 및 Microsoft Teams ATP 켜기 **확인란을** 선택하여 이 보호를 광범위하게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-257">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="4a6df-258">새 **+** 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-258">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="4a6df-259">다음 표의 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-259">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="4a6df-260">설정을 검토한 후 이  정책 만들기 또는 **저장을** 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-260">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="4a6df-261">설정 또는 옵션</span><span class="sxs-lookup"><span data-stu-id="4a6df-261">Setting or option</span></span>|<span data-ttu-id="4a6df-262">권장 설정</span><span class="sxs-lookup"><span data-stu-id="4a6df-262">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="4a6df-263">이름</span><span class="sxs-lookup"><span data-stu-id="4a6df-263">Name</span></span>|<span data-ttu-id="4a6df-264">감지된 맬웨어로 현재 및 향후 전자 메일을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-264">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="4a6df-265">설명</span><span class="sxs-lookup"><span data-stu-id="4a6df-265">Description</span></span>|<span data-ttu-id="4a6df-266">감지된 맬웨어로 현재 및 미래의 전자 메일 및 첨부 파일을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-266">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="4a6df-267">첨부 파일 알 수 없는 맬웨어 응답 저장</span><span class="sxs-lookup"><span data-stu-id="4a6df-267">Save attachments unknown malware response</span></span>|<span data-ttu-id="4a6df-268">차단 - 감지된 맬웨어로 현재 및 미래의 전자 메일 **및 첨부 파일을 차단을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-268">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="4a6df-269">검색 시 첨부 파일 리디렉션</span><span class="sxs-lookup"><span data-stu-id="4a6df-269">Redirect attachment on detection</span></span>|<span data-ttu-id="4a6df-270">리디렉션 사용(이 상자 선택) 관리자 계정 또는 사서함 설정을 입력하여 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-270">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="4a6df-271">첨부 파일에 대한 맬웨어 검색이 시간보다 멀거나 오류가 발생하는 경우 위의 선택을 적용합니다(이 상자 선택).</span><span class="sxs-lookup"><span data-stu-id="4a6df-271">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="4a6df-272">적용 대상</span><span class="sxs-lookup"><span data-stu-id="4a6df-272">Applied to</span></span>|<span data-ttu-id="4a6df-273">받는 사람 도메인은 입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-273">The recipient domain is .</span></span> <span data-ttu-id="4a6df-274">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-274">.</span></span> <span data-ttu-id="4a6df-275">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-275">.</span></span> <span data-ttu-id="4a6df-276">도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-276">select your domain.</span></span>|

<span data-ttu-id="4a6df-277">자세한 내용은 [Microsoft Defender에서](../security/office-365-security/set-up-anti-phishing-policies.md)피싱 방지 정책 Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a6df-277">For more information, see [Set up anti-phishing policies in Microsoft Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

## <a name="protect-against-phishing-attacks-with-safe-links"></a><span data-ttu-id="4a6df-278">안전한 링크를 통해 피싱 공격으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="4a6df-278">Protect against phishing attacks with Safe Links</span></span>

<span data-ttu-id="4a6df-279">해커가 전자 메일 또는 기타 파일의 링크에서 악성 웹 사이트를 숨기는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-279">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="4a6df-280">Microsoft Defender의 일부인 안전한 Office 365 전자 메일 메시지 및 문서에서 웹 주소(URL)의 클릭 시간 확인을 제공하여 조직을 보호할 Office 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-280">Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="4a6df-281">보호는 안전한 링크 정책을 통해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-281">Protection is defined through Safe Links policies.</span></span>

<span data-ttu-id="4a6df-282">다음을 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-282">We recommend that you do the following:</span></span>

- <span data-ttu-id="4a6df-283">보호를 강화하도록 기본 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-283">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="4a6df-284">도메인의 모든 받는 사람에게 대상으로 하는 새 정책을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-284">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="4a6df-285">안전한 링크를 설정하기 위해 이 짧은 교육 비디오를 [시청하거나](../business-video/safe-links.md)다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-285">To set up Safe Links, watch [this short training video](../business-video/safe-links.md), or complete the following steps:</span></span>

1. <span data-ttu-id="4a6df-286">로 [https://protection.office.com](https://protection.office.com) 이동하여 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-286">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="4a6df-287">보안 및 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 &amp; 정책을 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="4a6df-287">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="4a6df-288">정책 페이지에서 안전한 링크를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-288">On the Policy page, choose **Safe Links**.</span></span>

<span data-ttu-id="4a6df-289">기본 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="4a6df-289">To modify the default policy:</span></span>

1. <span data-ttu-id="4a6df-290">안전한 링크 페이지의 전체 조직에 적용되는 정책에서 **기본** **정책을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-290">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="4a6df-291">전자 **설정** 제외한 콘텐츠에 적용되는 응용 프로그램 아래에서 iOS 및 엔터프라이즈용 Microsoft 365 앱 Office **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a6df-291">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="4a6df-292">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-292">Select **Save**.</span></span>

<span data-ttu-id="4a6df-293">도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-293">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="4a6df-294">안전한 링크 페이지의 전체 조직에 적용되는 정책에서 **를** 선택하여 새 정책을 **+** 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-294">On the Safe links page, under **Policies that apply to the entire organization**, select **+** to create a new policy.</span></span>

2. <span data-ttu-id="4a6df-295">다음 표에 나열된 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-295">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="4a6df-296">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-296">Select **Save**.</span></span>

|<span data-ttu-id="4a6df-297">설정 또는 옵션</span><span class="sxs-lookup"><span data-stu-id="4a6df-297">Setting or option</span></span>|<span data-ttu-id="4a6df-298">권장 설정</span><span class="sxs-lookup"><span data-stu-id="4a6df-298">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="4a6df-299">이름</span><span class="sxs-lookup"><span data-stu-id="4a6df-299">Name</span></span>|<span data-ttu-id="4a6df-300">도메인의 모든 받는 사람에 대한 안전한 링크 정책</span><span class="sxs-lookup"><span data-stu-id="4a6df-300">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="4a6df-301">메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택</span><span class="sxs-lookup"><span data-stu-id="4a6df-301">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="4a6df-302">을 **선택합니다.** 사용자가 링크를 클릭할 때 알려진 악성 링크 목록과 관련한 URL이 다시 덮어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-302">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="4a6df-303">안전한 첨부 파일을 사용하여 다운로드 가능한 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="4a6df-303">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="4a6df-304">이 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-304">Select this box.</span></span>|
|<span data-ttu-id="4a6df-305">적용 대상</span><span class="sxs-lookup"><span data-stu-id="4a6df-305">Applied to</span></span>|<span data-ttu-id="4a6df-306">받는 사람 도메인은 입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-306">The recipient domain is .</span></span> <span data-ttu-id="4a6df-307">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-307">.</span></span> <span data-ttu-id="4a6df-308">.</span><span class="sxs-lookup"><span data-stu-id="4a6df-308">.</span></span> <span data-ttu-id="4a6df-309">도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-309">select your domain.</span></span>|

<span data-ttu-id="4a6df-310">자세한 내용은 안전한 링크를 [참조하세요.](../security/office-365-security/safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="4a6df-310">For more information, see [Safe Links](../security/office-365-security/safe-links.md).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="4a6df-311">Intune 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-311">Go to Intune admin center</span></span>

1. <span data-ttu-id="4a6df-312">[Azure Portal에 로그인합니다.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="4a6df-312">Sign in to [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="4a6df-313">**모든 서비스** 를 선택하고 **검색 상자** 에 *Intune* 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-313">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="4a6df-314">결과가 나타나면 나중에 쉽게 찾을  수 Microsoft Intune 만들기 위해 목록 옆에 있는 시작을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-314">Once the results appear, select the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="4a6df-315">관리 센터 외에도 Intune을 사용하여 조직의 장치를 등록하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6df-315">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="4a6df-316">자세한 내용은 Windows [](/intune/enrollment/enrollment-method-capab) 장치 등록 방법 및 [Intune에서](/intune/enrollment-options)관리하는 장치에 대한 등록 옵션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a6df-316">For more information, see [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) and [Enrollment options for devices managed by Intune](/intune/enrollment-options).</span></span>
