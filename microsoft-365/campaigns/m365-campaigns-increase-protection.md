---
title: 위협 방지 강화
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Microsoft 365에서 보호 수준 증가에 대한 도움말을 얻습니다.
ms.openlocfilehash: 0e8b63fec3b764f10039e9f738fd047ff2c513a4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052209"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a><span data-ttu-id="9b1c8-103">Microsoft 365 구독에 대한 위협 방지 강화</span><span class="sxs-lookup"><span data-stu-id="9b1c8-103">Increase threat protection for Microsoft 365 subscription</span></span>

<span data-ttu-id="9b1c8-104">이 문서는 피싱, 맬웨어 및 기타 위협으로부터 보호하기 위해 Microsoft 365 구독의 보호를 강화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="9b1c8-105">이러한 권장 사항은 정치적 캠페인, 법률 사무소 및 의료 기관과 같이 보안에 대한 필요성이 증가하는 조직에 적합한 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-105">These recommendations are appropriate for organizations with an increased need for security, like political campaigns, law offices, and health care clinics.</span></span>

<span data-ttu-id="9b1c8-106">시작하기 전에 Microsoft 보안 점수를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-106">Before you begin, check your Microsoft Secure Score.</span></span> <span data-ttu-id="9b1c8-107">Microsoft 보안 점수는 정기적인 활동 및 보안 설정에 따라 조직의 보안을 분석하고 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-107">Microsoft Secure Score analyzes your organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="9b1c8-108">먼저 현재 점수를 기록해 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="9b1c8-109">이 문서에서 권장하는 작업을 수행하면 점수가 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="9b1c8-110">목표는 최대 점수를 달성하는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호하기 위한 기회를 인식하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-110">The goal isn't to achieve the max score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="9b1c8-111">자세한 내용은 Microsoft 보안 점수를 [참조하세요.](../security/defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-111">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="9b1c8-112">메일의 맬웨어에 대한 보호 수준 높이기</span><span class="sxs-lookup"><span data-stu-id="9b1c8-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="9b1c8-113">Office 365 또는 Microsoft 365 환경에는 맬웨어에 대한 보호가 포함되어 있지만 맬웨어에 일반적으로 사용되는 파일 형식의 첨부 파일을 차단하여 이 보호를 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="9b1c8-114">전자 메일에서 맬웨어 보호를 범프합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-114">To bump up malware protection in email:</span></span>

1. <span data-ttu-id="9b1c8-115">으로 <https://protection.office.com> 이동하여 관리자 계정 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-115">Go to <https://protection.office.com> and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="9b1c8-116">보안 및 & 센터의 왼쪽 탐색 창에 있는 **위협** 관리에서  정책 맬웨어 방지 \> **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-116">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="9b1c8-117">기본 정책을 두 번 클릭하여 이 회사 전체 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-117">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="9b1c8-118">**설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-118">Click **Settings**.</span></span>

5. <span data-ttu-id="9b1c8-119">일반 **첨부 파일 형식 필터에서** 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="9b1c8-120">차단된 파일 형식은 이 컨트롤 바로 아래에 있는 창에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-120">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="9b1c8-121">다음 파일 형식을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-121">Make sure you add these filetypes:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="9b1c8-122">필요한 경우 나중에 파일 형식을 추가하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-122">You can add or delete file types later, if needed.</span></span>

6. <span data-ttu-id="9b1c8-123">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-123">Click **Save.**</span></span>

<span data-ttu-id="9b1c8-124">자세한 내용은 [EOP의 맬웨어 방지 보호를 참조하세요.](../security/defender-365-security/anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-124">For more information, see [Anti-malware protection in EOP](../security/defender-365-security/anti-malware-protection.md).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="9b1c8-125">랜섬웨어로부터 보호</span><span class="sxs-lookup"><span data-stu-id="9b1c8-125">Protect against ransomware</span></span>

<span data-ttu-id="9b1c8-126">랜섬웨어는 파일을 암호화하거나 컴퓨터 화면을 잠가 데이터에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-126">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="9b1c8-127">그런 다음 데이터에 대한 액세스 대가로 일반적으로 가상화 형식의 "금전"을 요청하여 피해자로부터 돈을 유출하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-127">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="9b1c8-128">랜섬웨어에 일반적으로 사용되는 파일 확장명을 차단하는 메일 흐름 규칙을 하나 이상 만들어 랜섬웨어로부터 보호하거나(메일 단계에서 맬웨어에 대한 보호 수준 높이기에서 추가) 전자 메일로 이러한 첨부 파일을 받는 사용자에게 경고할 수 있습니다. [](#raise-the-level-of-protection-against-malware-in-mail)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-128">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="9b1c8-129">이전 단계에서 차단한 파일 외에도 매크로가 포함된 Office 첨부 파일을 열기 전에 사용자에게 경고하는 규칙을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-129">In addition to the files that you blocked in the previous step, it's also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="9b1c8-130">매크로 내에서 랜섬웨어를 숨길 수 있으므로 모르는 사용자로부터 이러한 파일을 열지 못하게 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-130">Ransomware can be hidden inside macros, so warn users to not open these files from people they don't know.</span></span>

<span data-ttu-id="9b1c8-131">메일 전송 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-131">To create a mail transport rule:</span></span>

1. <span data-ttu-id="9b1c8-132">의 관리 센터로 <https://admin.microsoft.com> 이동하여 관리 센터 Exchange **를** \> **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-132">Go to the admin center at <https://admin.microsoft.com> and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="9b1c8-133">메일 **흐름 범주에서** 규칙을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-133">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="9b1c8-134">**+** 를 클릭한 다음 새 규칙 **만들기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-134">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="9b1c8-135">대화 **상자 아래쪽의** 다른 옵션을 클릭하여 전체 옵션 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-135">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="9b1c8-136">규칙에 대한 다음 표의 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-136">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="9b1c8-137">나머지 설정을 변경하지 않는 한 나머지 설정을 기본값으로 그대로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-137">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="9b1c8-138">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-138">Click **Save**.</span></span>

|<span data-ttu-id="9b1c8-139">설정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-139">Setting</span></span>|<span data-ttu-id="9b1c8-140">Office 파일의 첨부 파일을 열기 전에 사용자에게 경고</span><span class="sxs-lookup"><span data-stu-id="9b1c8-140">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="9b1c8-141">이름</span><span class="sxs-lookup"><span data-stu-id="9b1c8-141">Name</span></span>|<span data-ttu-id="9b1c8-142">랜섬웨어 방지 규칙: 사용자에게 경고</span><span class="sxs-lookup"><span data-stu-id="9b1c8-142">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="9b1c8-143">이 경우 이 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-143">Apply this rule if .</span></span> <span data-ttu-id="9b1c8-144">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-144">.</span></span> <span data-ttu-id="9b1c8-145">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-145">.</span></span>|<span data-ttu-id="9b1c8-146">모든 첨부 파일 .</span><span class="sxs-lookup"><span data-stu-id="9b1c8-146">Any attachment .</span></span> <span data-ttu-id="9b1c8-147">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-147">.</span></span> <span data-ttu-id="9b1c8-148">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-148">.</span></span> <span data-ttu-id="9b1c8-149">파일 확장명은 을 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-149">file extension matches .</span></span> <span data-ttu-id="9b1c8-150">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-150">.</span></span> <span data-ttu-id="9b1c8-151">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-151">.</span></span>|
|<span data-ttu-id="9b1c8-152">단어 또는 구 지정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-152">Specify words or phrases</span></span>|<span data-ttu-id="9b1c8-153">다음 파일 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-153">Add these file types:</span></span> <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|<span data-ttu-id="9b1c8-154">다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-154">Do the following .</span></span> <span data-ttu-id="9b1c8-155">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-155">.</span></span> <span data-ttu-id="9b1c8-156">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-156">.</span></span>|<span data-ttu-id="9b1c8-157">받는 사람에게 메시지로 알림</span><span class="sxs-lookup"><span data-stu-id="9b1c8-157">Notify the recipient with a message</span></span>|
|<span data-ttu-id="9b1c8-158">메시지 텍스트 제공</span><span class="sxs-lookup"><span data-stu-id="9b1c8-158">Provide message text</span></span>|<span data-ttu-id="9b1c8-159">악성 코드가 포함된 매크로가 포함되어 있을 수 있기 때문에 모르는 사용자로부터 이러한 형식의 파일을 열지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-159">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="9b1c8-160">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-160">For more information, see:</span></span>

- [<span data-ttu-id="9b1c8-161">랜섬웨어: 위험을 줄이는 방법</span><span class="sxs-lookup"><span data-stu-id="9b1c8-161">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="9b1c8-162">OneDrive 복원</span><span class="sxs-lookup"><span data-stu-id="9b1c8-162">Restore your OneDrive</span></span>](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="9b1c8-163">전자 메일에 대한 자동 전달 중지</span><span class="sxs-lookup"><span data-stu-id="9b1c8-163">Stop auto-forwarding for email</span></span>

<span data-ttu-id="9b1c8-164">사용자의 사서함에 액세스할 수 있는 해커는 사서함이 자동으로 전자 메일을 전달하도록 설정하여 메일을 도용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-164">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="9b1c8-165">이는 사용자의 인식 없이도 발생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-165">This can happen even without the user's awareness.</span></span> <span data-ttu-id="9b1c8-166">메일 흐름 규칙을 구성하여 이러한 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-166">You can prevent this from happening by configuring a mail flow rule.</span></span>

<span data-ttu-id="9b1c8-167">메일 전송 규칙을 만들 수 [](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) 있는 경우 이 짧은 비디오를 시청하거나 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-167">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="9b1c8-168">Microsoft 365 관리 센터에서 관리 센터 Exchange **를** \> **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-168">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="9b1c8-169">메일 **흐름 범주에서** 규칙을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-169">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="9b1c8-170">**+** 를 클릭한 다음 새 규칙 **만들기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-170">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="9b1c8-171">대화 **상자 아래쪽의** 다른 옵션을 클릭하여 전체 옵션 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-171">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="9b1c8-172">다음 표의 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-172">Apply the settings in the following table.</span></span> <span data-ttu-id="9b1c8-173">나머지 설정을 변경하지 않는 한 나머지 설정을 기본값으로 그대로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-173">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="9b1c8-174">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-174">Click **Save**.</span></span>

|<span data-ttu-id="9b1c8-175">설정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-175">Setting</span></span>|<span data-ttu-id="9b1c8-176">Office 파일의 첨부 파일을 열기 전에 사용자에게 경고</span><span class="sxs-lookup"><span data-stu-id="9b1c8-176">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="9b1c8-177">이름</span><span class="sxs-lookup"><span data-stu-id="9b1c8-177">Name</span></span>|<span data-ttu-id="9b1c8-178">외부 도메인으로 전자 메일 자동 전달 방지</span><span class="sxs-lookup"><span data-stu-id="9b1c8-178">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="9b1c8-179">다음의 경우 이 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-179">Apply this rule if ...</span></span>|<span data-ttu-id="9b1c8-180">보낸 사람 입니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-180">The sender .</span></span> <span data-ttu-id="9b1c8-181">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-181">.</span></span> <span data-ttu-id="9b1c8-182">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-182">.</span></span> <span data-ttu-id="9b1c8-183">은 외부/내부입니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-183">is external/internal .</span></span> <span data-ttu-id="9b1c8-184">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-184">.</span></span> <span data-ttu-id="9b1c8-185">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-185">.</span></span> <span data-ttu-id="9b1c8-186">조직 내부</span><span class="sxs-lookup"><span data-stu-id="9b1c8-186">Inside the organization</span></span>|
|<span data-ttu-id="9b1c8-187">조건 추가</span><span class="sxs-lookup"><span data-stu-id="9b1c8-187">Add condition</span></span>|<span data-ttu-id="9b1c8-188">메시지 속성 입니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-188">The message properties .</span></span> <span data-ttu-id="9b1c8-189">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-189">.</span></span> <span data-ttu-id="9b1c8-190">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-190">.</span></span> <span data-ttu-id="9b1c8-191">메시지 유형 을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-191">include the message type .</span></span> <span data-ttu-id="9b1c8-192">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-192">.</span></span> <span data-ttu-id="9b1c8-193">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-193">.</span></span> <span data-ttu-id="9b1c8-194">자동 전달</span><span class="sxs-lookup"><span data-stu-id="9b1c8-194">Auto-forward</span></span>|
|<span data-ttu-id="9b1c8-195">다음 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-195">Do the following ...</span></span>|<span data-ttu-id="9b1c8-196">메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-196">Block the message .</span></span> <span data-ttu-id="9b1c8-197">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-197">.</span></span> <span data-ttu-id="9b1c8-198">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-198">.</span></span> <span data-ttu-id="9b1c8-199">메시지를 거부하고 설명을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-199">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="9b1c8-200">메시지 텍스트 제공</span><span class="sxs-lookup"><span data-stu-id="9b1c8-200">Provide message text</span></span>|<span data-ttu-id="9b1c8-201">보안상의 이유로 이 조직 외부에서 전자 메일을 자동 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-201">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|

## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="9b1c8-202">피싱 공격으로부터 전자 메일 보호</span><span class="sxs-lookup"><span data-stu-id="9b1c8-202">Protect your email from phishing attacks</span></span>

<span data-ttu-id="9b1c8-203">Office 365 또는 Microsoft 365 환경에 대해 하나 이상의 사용자 지정 도메인을 구성한 경우 대상 피싱 방지 보호를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-203">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="9b1c8-204">Microsoft Defender for Office 365의 일부인 피싱 방지 보호는 악의적인 가장 기반 피싱 공격 및 기타 피싱 공격으로부터 조직을 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-204">Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="9b1c8-205">사용자 지정 도메인을 구성하지 않은 경우 이 작업을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-205">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="9b1c8-206">가장 중요한 사용자와 사용자 지정 도메인을 보호하는 정책을 만들어 이 보호를 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-206">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="9b1c8-207">Office 365용 Defender에서 피싱 방지 정책을 만들거나 이 짧은 교육 비디오를 시청하거나 다음 단계를 완료합니다. [](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-207">To create an anti-phishing policy in Defender for Office 365, watch [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="9b1c8-208"><https://protection.office.com>으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-208">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="9b1c8-209">보안 및 & 센터의 왼쪽 탐색 창에 있는 **위협** 관리에서 정책을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-209">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="9b1c8-210">정책 **페이지에서** 피싱 **방지 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-210">On the **Policy** page, choose **Anti-phishing**.</span></span>

4. <span data-ttu-id="9b1c8-211">피싱 **방지 페이지에서** + **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-211">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="9b1c8-212">피싱 방지 정책을 정의하는 단계를 안내하는 마법사가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-212">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="9b1c8-213">아래 차트에서 권장되는 정책의 이름, 설명 및 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-213">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="9b1c8-214">자세한 내용은 [Microsoft Defender for Office 365](../security/defender-365-security/set-up-anti-phishing-policies.md)옵션에서 피싱 방지 정책에 대한 자세한 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-214">For more information, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/defender-365-security/set-up-anti-phishing-policies.md).</span></span>

6. <span data-ttu-id="9b1c8-215">설정을 검토한 후 이 정책  만들기 또는 **저장을** 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-215">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="9b1c8-216">설정 또는 옵션</span><span class="sxs-lookup"><span data-stu-id="9b1c8-216">Setting or option</span></span>|<span data-ttu-id="9b1c8-217">권장 설정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-217">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="9b1c8-218">이름</span><span class="sxs-lookup"><span data-stu-id="9b1c8-218">Name</span></span>|<span data-ttu-id="9b1c8-219">도메인 및 가장 중요한 직원</span><span class="sxs-lookup"><span data-stu-id="9b1c8-219">Domain and most valuable staff</span></span>|
|<span data-ttu-id="9b1c8-220">설명</span><span class="sxs-lookup"><span data-stu-id="9b1c8-220">Description</span></span>|<span data-ttu-id="9b1c8-221">가장 중요한 직원과 도메인이 가장되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-221">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="9b1c8-222">보호할 사용자를 추가</span><span class="sxs-lookup"><span data-stu-id="9b1c8-222">Add users to protect</span></span>|<span data-ttu-id="9b1c8-223">+ **조건 추가를 선택합니다. 받는 사람은 입니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-223">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="9b1c8-224">사용자 이름을 입력하거나 비즈니스 소유자, 파트너 또는 후보, 관리자 및 기타 중요한 직원 구성원의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-224">Type user names or enter the email address of the business owners, partners, or candidate, managers, and other important staff members.</span></span> <span data-ttu-id="9b1c8-225">가장으로부터 보호할 내부 및 외부 주소를 최대 20개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-225">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="9b1c8-226">보호할 도메인을 추가</span><span class="sxs-lookup"><span data-stu-id="9b1c8-226">Add domains to protect</span></span>|<span data-ttu-id="9b1c8-227">+ **조건 추가를 선택하고 받는 사람 도메인은 입니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-227">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="9b1c8-228">정의한 경우 Microsoft 365 구독과 연결된 사용자 지정 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-228">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="9b1c8-229">두 개 이상의 도메인을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-229">You can enter more than one domain.</span></span>|
|<span data-ttu-id="9b1c8-230">작업 선택</span><span class="sxs-lookup"><span data-stu-id="9b1c8-230">Choose actions</span></span>|<span data-ttu-id="9b1c8-231">가장된 사용자가 전자 메일을 보낸 경우: **메시지를** 다른 전자 메일 주소로 리디렉션을 선택한 다음 보안 관리자의 전자 메일 주소를 입력합니다. 예를 들어 *Alice <span> <span> @contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="9b1c8-231">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <br/> <span data-ttu-id="9b1c8-232">가장된 도메인에서 전자 메일을 보내는 경우: **격리 메시지** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-232">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="9b1c8-233">사서함 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="9b1c8-233">Mailbox intelligence</span></span>|<span data-ttu-id="9b1c8-234">새 피싱 방지 정책을 만들 때 기본적으로 사서함 인텔리전스가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-234">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="9b1c8-235">최상의 결과를 위해 해당 설정을 **켜짐** 에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-235">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="9b1c8-236">신뢰할 수 있는 발신자와 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="9b1c8-236">Add trusted senders and domains</span></span>|<span data-ttu-id="9b1c8-237">여기에서 자체 도메인 또는 기타 신뢰할 수 있는 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-237">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="9b1c8-238">적용 대상</span><span class="sxs-lookup"><span data-stu-id="9b1c8-238">Applied to</span></span>|<span data-ttu-id="9b1c8-239">**받는 사람의 도메인이 다음과 같음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-239">Select **The recipient domain is**.</span></span> <span data-ttu-id="9b1c8-240">**이러한 항목 모두** 아래에서 **선택** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-240">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="9b1c8-241">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-241">Select **+ Add**.</span></span> <span data-ttu-id="9b1c8-242">도메인 이름 옆의 확인란(예: *contoso)을 선택합니다. <span> <span> 목록에서 com* 을 선택하고 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-242">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="9b1c8-243">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-243">Select **Done**.</span></span>|

<span data-ttu-id="9b1c8-244">자세한 내용은 [Office 365용 Defender에서](../security/defender-365-security/set-up-anti-phishing-policies.md)피싱 방지 정책 설정 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-244">For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/defender-365-security/set-up-anti-phishing-policies.md).</span></span>

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a><span data-ttu-id="9b1c8-245">Office 365용 Defender를 통해 악의적인 첨부 파일, 파일 및 링크로부터 보호</span><span class="sxs-lookup"><span data-stu-id="9b1c8-245">Protect against malicious attachments, files, and links with Defender for Office 365</span></span>

![을(를) 포인트로 하는 https://aka.ms/aboutM365preview 배너입니다.](../media/m365admincenterchanging.png)

<span data-ttu-id="9b1c8-247">먼저 관리 센터에서 새 관리 센터 미리 보기가 <https://admin.microsoft.com> 켜져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-247">First, make sure, in the admin center at <https://admin.microsoft.com> that you have the new admin center preview turned on.</span></span> <span data-ttu-id="9b1c8-248">텍스트 옆에 있는 토글을 켜면 새 **관리 센터 입니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-248">Turn on the toggle next to the text **The new admin center**.</span></span>

   ![새 관리 센터 미리 보기가 설정됩니다.](../media/previewon.png)

<span data-ttu-id="9b1c8-250">테넌트에 카드가  있는 설치 페이지가 아직 없는 경우 보안 및 준수 센터에서 & 완료하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-250">If you don't see the **Setup** page with cards in your tenant yet, see how to complete these steps in Security & Compliance Center.</span></span> <span data-ttu-id="9b1c8-251">보안 [및 준수](#set-up-safe-attachments-in-the-security--compliance-center) 센터에서 안전한 첨부 & 설정 및 보안 및 준수 센터에서 안전한 & [을 참조하세요.](#set-up-safe-links-in-the-security--compliance-center)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-251">See [Set up Safe Attachments in the Security & Compliance Center](#set-up-safe-attachments-in-the-security--compliance-center) and [Set up Safe Links in the Security & Compliance Center](#set-up-safe-links-in-the-security--compliance-center).</span></span>

1. <span data-ttu-id="9b1c8-252">In the left nav, choose **Setup**.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-252">In the left nav, choose **Setup**.</span></span>
2. <span data-ttu-id="9b1c8-253">설치 **페이지에서** 고급 **위협으로부터** 보호 강화 **카드에서 보기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-253">On the **Setup** page, choose **View** on the **Increase protection from advanced threats** card.</span></span>

   ![고급 위협으로부터 보호 강화에서 보기를 선택하십시오.](../media/startatp.png)

3. <span data-ttu-id="9b1c8-255">고급 **위협으로부터 보호 강화 페이지에서** 시작 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-255">On the **Increase protection from advanced threats** page, choose **Get started**.</span></span>
4. <span data-ttu-id="9b1c8-256">창이 열리면 전자 메일의 링크 및 첨부 **파일,** **SharePoint, OneDrive** 및 Teams에서 파일 검색 옆의 확인란을 선택하고, Office 데스크톱 및 **Office Online** 앱의 링크 검사에서 악성 콘텐츠에 대한 항목 검색 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-256">On the pane that opens, select the check boxes next to **Links and attachments in email**, **Scan files in SharePoint, OneDrive, and Teams**, and **Scan links in Office desktop and Office Online apps** under **Scan items for malicious content**.</span></span>

   <span data-ttu-id="9b1c8-257">전자 메일의 링크 **및 첨부 파일에서** 모든 사용자 또는 전자 메일을 검사할 특정 사용자를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-257">Under **Links and attachments in email**, Type in All Users, or the specific users whose email you want scanned.</span></span>

   ![고급 위협으로부터 보호 강화의 모든 확인란을 선택합니다.](../media/setatp.png)

5. <span data-ttu-id="9b1c8-259">정책 **만들기를** 선택하면 안전한 첨부 파일 및 안전한 링크를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-259">Choose **Create policies** to turn on Safe Attachments and Safe Links.</span></span>

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a><span data-ttu-id="9b1c8-260">보안 및 준수 센터에서 안전한 첨부 & 설정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-260">Set up Safe Attachments in the Security & Compliance Center</span></span>

<span data-ttu-id="9b1c8-261">문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-261">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="9b1c8-262">전자 메일 메시지를 확인하여 첨부 파일이 안전한지 악성인지를 항상 쉽게 알 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-262">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="9b1c8-263">Office 365용 Microsoft Defender에는 안전한 첨부 파일 보호가 포함되어 있지만 이 보호는 기본적으로 켜져 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-263">Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="9b1c8-264">이 보호를 사용하 여 시작 하는 새 규칙을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-264">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="9b1c8-265">이 보호는 SharePoint, OneDrive 및 Microsoft Teams의 파일로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-265">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="9b1c8-266">안전한 첨부 파일 정책을 만들거나 [](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)이 짧은 비디오를 시청하거나 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-266">To create an Safe Attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="9b1c8-267">으로 <https://protection.office.com> 이동하여 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-267">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="9b1c8-268">보안 및 & 센터의 왼쪽 탐색 창에 있는 **위협** 관리에서 정책을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-268">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="9b1c8-269">정책 페이지에서 안전한 첨부 **파일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-269">On the Policy page, choose **Safe Attachments**.</span></span>

4. <span data-ttu-id="9b1c8-270">안전한 첨부 파일 페이지에서 **SharePoint, OneDrive 및 Microsoft Teams에 대해 ATP** 켜기 확인란을 선택하여 이 보호를 광범위하게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-270">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="9b1c8-271">새 **+** 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-271">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="9b1c8-272">다음 표의 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-272">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="9b1c8-273">설정을 검토한 후 이 **정책** 만들기 또는 **저장을** 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-273">After you review your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="9b1c8-274">설정 또는 옵션</span><span class="sxs-lookup"><span data-stu-id="9b1c8-274">Setting or option</span></span>|<span data-ttu-id="9b1c8-275">권장 설정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-275">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="9b1c8-276">이름</span><span class="sxs-lookup"><span data-stu-id="9b1c8-276">Name</span></span>|<span data-ttu-id="9b1c8-277">감지된 맬웨어로 현재 및 향후 전자 메일을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-277">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="9b1c8-278">설명</span><span class="sxs-lookup"><span data-stu-id="9b1c8-278">Description</span></span>|<span data-ttu-id="9b1c8-279">감지된 맬웨어로 현재 및 미래의 전자 메일 및 첨부 파일을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-279">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="9b1c8-280">첨부 파일 알 수 없는 맬웨어 응답 저장</span><span class="sxs-lookup"><span data-stu-id="9b1c8-280">Save attachments unknown malware response</span></span>|<span data-ttu-id="9b1c8-281">차단 - 감지된 맬웨어로 현재 및 미래의 전자 메일 **및 첨부 파일을 차단을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-281">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="9b1c8-282">검색 시 첨부 파일 리디렉션</span><span class="sxs-lookup"><span data-stu-id="9b1c8-282">Redirect attachment on detection</span></span>|<span data-ttu-id="9b1c8-283">리디렉션 사용(이 상자 선택)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-283">Enable redirection (select this box)</span></span> <br/> <span data-ttu-id="9b1c8-284">관리자 계정 또는 사서함 설정을 입력하여 검지합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-284">Enter the admin account or a mailbox setup for quarantine.</span></span> <br/> <span data-ttu-id="9b1c8-285">첨부 파일에 대한 맬웨어 검색이 시간보다 멀거나 오류가 발생하는 경우 위의 선택을 적용합니다(이 상자 선택).</span><span class="sxs-lookup"><span data-stu-id="9b1c8-285">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="9b1c8-286">적용 대상</span><span class="sxs-lookup"><span data-stu-id="9b1c8-286">Applied to</span></span>|<span data-ttu-id="9b1c8-287">받는 사람 도메인은 입니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-287">The recipient domain is .</span></span> <span data-ttu-id="9b1c8-288">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-288">.</span></span> <span data-ttu-id="9b1c8-289">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-289">.</span></span> <span data-ttu-id="9b1c8-290">도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-290">select your domain.</span></span>|

<span data-ttu-id="9b1c8-291">자세한 내용은 [Office 365용 Defender에서](../security/defender-365-security/set-up-anti-phishing-policies.md)피싱 방지 정책 설정 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-291">For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/defender-365-security/set-up-anti-phishing-policies.md).</span></span>

### <a name="set-up-safe-links-in-the-security--compliance-center"></a><span data-ttu-id="9b1c8-292">보안 및 준수 센터에서 안전한 & 설정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-292">Set up Safe Links in the Security & Compliance Center</span></span>

<span data-ttu-id="9b1c8-293">해커가 전자 메일 또는 기타 파일의 링크에서 악성 웹 사이트를 숨기는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-293">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="9b1c8-294">Office 365용 Microsoft Defender의 일부인 안전한 링크는 전자 메일 메시지 및 Office 문서에서 웹 주소(URL)의 클릭 시간 확인을 제공하여 조직을 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-294">Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="9b1c8-295">보호는 안전한 링크 정책을 통해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-295">Protection is defined through Safe Links policies.</span></span>

<span data-ttu-id="9b1c8-296">다음을 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-296">We recommend that you do the following:</span></span>

- <span data-ttu-id="9b1c8-297">보호를 강화하도록 기본 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-297">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="9b1c8-298">도메인의 모든 받는 사람에게 대상으로 하는 새 정책을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-298">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="9b1c8-299">안전한 링크를 설정하기 위해 이 짧은 교육 비디오를 [시청하거나](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-299">To set up Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="9b1c8-300">으로 <https://protection.office.com> 이동하여 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-300">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="9b1c8-301">보안 및 & 센터의 왼쪽 탐색 창에 있는 **위협** 관리에서 정책을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-301">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="9b1c8-302">정책 페이지에서 안전한 링크를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-302">On the Policy page, choose **Safe Links**.</span></span>

<span data-ttu-id="9b1c8-303">기본 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="9b1c8-303">To modify the default policy:</span></span>

1. <span data-ttu-id="9b1c8-304">안전한 링크 페이지의 전체 조직에 적용되는 정책에서 **기본** **정책을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-304">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="9b1c8-305">전자 **메일을 제외한 콘텐츠에** 적용되는 설정에서 **엔터프라이즈용 Microsoft 365 앱, iOS용 Office 및 Android를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-305">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="9b1c8-306">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-306">Click **Save**.</span></span>

<span data-ttu-id="9b1c8-307">도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-307">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="9b1c8-308">안전한 링크 페이지의 전체 조직에 적용되는 정책에서 **를** 클릭하여 새 정책을 **+** 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-308">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span>

2. <span data-ttu-id="9b1c8-309">다음 표에 나열된 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-309">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="9b1c8-310">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-310">Click **Save**.</span></span>

|<span data-ttu-id="9b1c8-311">설정 또는 옵션</span><span class="sxs-lookup"><span data-stu-id="9b1c8-311">Setting or option</span></span>|<span data-ttu-id="9b1c8-312">권장 설정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-312">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="9b1c8-313">이름</span><span class="sxs-lookup"><span data-stu-id="9b1c8-313">Name</span></span>|<span data-ttu-id="9b1c8-314">도메인의 모든 받는 사람에 대한 안전한 링크 정책</span><span class="sxs-lookup"><span data-stu-id="9b1c8-314">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="9b1c8-315">메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택</span><span class="sxs-lookup"><span data-stu-id="9b1c8-315">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="9b1c8-316">을 **선택합니다.** 사용자가 링크를 클릭할 때 알려진 악성 링크 목록과 관련한 URL이 다시 덮어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-316">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="9b1c8-317">안전한 첨부 파일을 사용하여 다운로드 가능한 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="9b1c8-317">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="9b1c8-318">이 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-318">Select this box.</span></span>|
|<span data-ttu-id="9b1c8-319">적용 대상</span><span class="sxs-lookup"><span data-stu-id="9b1c8-319">Applied to</span></span>|<span data-ttu-id="9b1c8-320">받는 사람 도메인은 입니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-320">The recipient domain is .</span></span> <span data-ttu-id="9b1c8-321">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-321">.</span></span> <span data-ttu-id="9b1c8-322">.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-322">.</span></span> <span data-ttu-id="9b1c8-323">도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-323">select your domain.</span></span>|

<span data-ttu-id="9b1c8-324">자세한 내용은 [Defender for Office 365의 안전한 링크를 참조하세요.](../security/defender-365-security/safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-324">For more information, see [Safe Links in Defender for Office 365](../security/defender-365-security/safe-links.md).</span></span>

## <a name="turn-on-the-unified-audit-log"></a><span data-ttu-id="9b1c8-325">통합 감사 로그 켜기</span><span class="sxs-lookup"><span data-stu-id="9b1c8-325">Turn on the Unified Audit Log</span></span>

<span data-ttu-id="9b1c8-326">보안 및 준수 센터에서 감사 로그 검색을 & 로그에 관리자 및 기타 사용자 활동을 보존하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-326">After you turn on the audit log search in the Security & Compliance Center, you can retain the admin and other user activity in the log and search it.</span></span>

<span data-ttu-id="9b1c8-327">Microsoft 365 구독에서 감사 로그 검색을 설정하거나 해제하려면 Exchange Online에서 감사 로그 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-327">You must be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 subscription.</span></span> <span data-ttu-id="9b1c8-328">기본적으로 이 역할은 Exchange 관리 센터의 사용 권한 페이지에서 준수 관리 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-328">By default, this role is assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="9b1c8-329">Microsoft 365의 전역 관리자는 기본적으로 이 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-329">Global admins in Microsoft 365 are members of this group by default.</span></span>

1. <span data-ttu-id="9b1c8-330">감사 로그 검색을 켜기 위해 의 관리 센터로 이동한 다음 왼쪽 탐색의 관리 센터에서 보안을 <https://admin.microsoft.com> 선택하세요.  </span><span class="sxs-lookup"><span data-stu-id="9b1c8-330">To turn on the audit log search, go to the admin center at <https://admin.microsoft.com> and then choose **Security** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="9b1c8-331">Microsoft **365 보안** 페이지에서 추가 리소스 를 선택한 다음 **Office 365** 보안 및 준수 센터 & 를 니다. </span><span class="sxs-lookup"><span data-stu-id="9b1c8-331">On the **Microsoft 365 Security** page, choose **More resources**, and then **Open** on the **Office 365 Security & Compliance Center** card.</span></span>

    ![보안 및 준수 자동차에서 & 를 선택 합니다.](../media/gotosecandcomp.png)
3. <span data-ttu-id="9b1c8-333">보안 및 준수 페이지에서 검색을 **선택한** 다음 로그 검색 **감사 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-333">On the security and compliance page, choose **Search** and then **Audit log search**.</span></span>
4. <span data-ttu-id="9b1c8-334">감사 로그 **검색** 페이지의 맨 위에 있는 감사 **켜기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-334">On the top of the **Audit log search** page, choose **Turn on auditing**.</span></span>

<span data-ttu-id="9b1c8-335">기능이 켜진 후 파일, 폴더 및 여러 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-335">After the feature is turned on, you can search for files, folders, and many activities.</span></span> <span data-ttu-id="9b1c8-336">자세한 내용은 감사 로그 [검색을 참조하세요.](../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-336">For more information, see [search the audit log](../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a><span data-ttu-id="9b1c8-337">SharePoint 및 OneDrive 파일 및 폴더에 대한 익명 공유 설정 조정</span><span class="sxs-lookup"><span data-stu-id="9b1c8-337">Tune-up anonymous sharing settings for SharePoint and OneDrive files and folders</span></span>

<span data-ttu-id="9b1c8-338">기본 익명 링크 만료를 14일로 변경하고 기본 공유 유형을 "특정 사용자"로 변경) OneDrive 및 SharePoint의 공유 설정을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="9b1c8-338">(change default anonymous link expiration to 14 days, change default sharing type to "Specific People") To change the sharing settings for OneDrive and SharePoint:</span></span>

1. <span data-ttu-id="9b1c8-339">의 관리 센터로 이동한 다음 왼쪽 네비게이트의 관리 센터에서 <https://admin.microsoft.com> **SharePoint를** 선택하세요. </span><span class="sxs-lookup"><span data-stu-id="9b1c8-339">Go to the admin center at <https://admin.microsoft.com> and then choose **SharePoint** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="9b1c8-340">SharePoint 관리 센터에서 정책 공유 **로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-340">In the SharePoint admin center, go to **Policies** \> **Sharing**.</span></span>
3. <span data-ttu-id="9b1c8-341">공유  페이지의 파일 및 폴더 링크에서  **특정** 사용자 및 **"모든 사용자"** 링크의 고급 설정에서 이러한 링크가 이 기간 내에 만료되어야 합니다.를 선택하고 14(또는 링크 수명을 제한하려는 다른 일 수)를 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="9b1c8-341">On the **Sharing** page, under **File and folder links**, select **Specific people**, and under **Advanced settings for "Anyone" links**, select **These links must expire within this many days**, and type in 14 (or another number of days you want to restrict the link lifetime to).</span></span>

   ![특정 사용자 및 링크 만료를 14일로 설정](../media/anyonelinks.png)

## <a name="activity-alerts"></a><span data-ttu-id="9b1c8-343">활동 알림</span><span class="sxs-lookup"><span data-stu-id="9b1c8-343">Activity alerts</span></span>

<span data-ttu-id="9b1c8-344">활동 알림을 사용하여 관리자 및 사용자 활동을 추적하고 조직의 맬웨어 및 데이터 손실 방지 인시던트 감지를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-344">You can use activity alerts to track admin and user activities and detect malware and data loss prevention incidents in your organization.</span></span> <span data-ttu-id="9b1c8-345">구독에는 기본 정책 집합이 포함되어 있지만 사용자 지정 정책 집합을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-345">Your subscription includes a set of default policies, but you can also create custom ones.</span></span> <span data-ttu-id="9b1c8-346">자세한 내용은 경고 정책을 [참조하세요.](../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9b1c8-346">For more information, see [alert policies](../compliance/alert-policies.md).</span></span> <span data-ttu-id="9b1c8-347">예를 들어 누구도 외부에서 공유하지 않는 중요한 파일을 SharePoint에 저장하는 경우 다른 사용자가 공유하는 경우 알림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-347">For example, if you store an important file in SharePoint that you don't want anyone to share externally, you can create a notification that alerts you if someone does share it.</span></span>

<span data-ttu-id="9b1c8-348">다음 그림에서는 Microsoft 365에 포함된 기본 정책을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-348">The following figure shows the default policies that are included with Microsoft 365.</span></span>

![Microsoft 365에 포함된 기본 경고 정책](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a><span data-ttu-id="9b1c8-350">일정 공유를 사용하지 않도록 설정하거나 관리</span><span class="sxs-lookup"><span data-stu-id="9b1c8-350">Disable or manage calendar sharing</span></span>

<span data-ttu-id="9b1c8-351">조직의 사용자가 일정을 공유하지 못하게 할 수도 있습니다. 또는 공유할 수 있는 것을 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-351">You can prevent people in your organization from sharing their calendars, or you can also manage what they can share.</span></span> <span data-ttu-id="9b1c8-352">예를 들어 공유를 사용/사용 중 시간으로만 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-352">For example, you can restrict the sharing to free/busy times only.</span></span>

1. <span data-ttu-id="9b1c8-353">의 관리 센터로 <https://admin.microsoft.com> 이동하여 **설정** \> **구성 설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b1c8-353">Go to the admin center at <https://admin.microsoft.com> and choose **Settings** \> **Org Settings**.</span></span>
2. <span data-ttu-id="9b1c8-354">서비스 **페이지에서** 일정 을 선택하고 조직의 사용자들이 Office 365 또는 Exchange가 있는 외부의 사용자와 일정을 공유할 수 있는지 또는 다른 사용자와 일정을 공유할 수 있는지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-354">On the **Services** page, choose **Calendar**, and choose whether people in your organization can share their calendars with people outside who have Office 365 or Exchange, or with anyone.</span></span>

   <span data-ttu-id="9b1c8-355">모든 사용자와 공유 옵션을 선택하는 경우 사용 중 정보만 공유하기로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-355">If you choose the share with anyone option, you can decide to also only share free/busy information.</span></span>

3. <span data-ttu-id="9b1c8-356">페이지 **아래쪽의** 변경 내용 저장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-356">Choose **Save changes** on the bottom of the page.</span></span>

   <span data-ttu-id="9b1c8-357">다음 그림에서는 일정 공유를 허용하지 않는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-357">The following figure shows calendar sharing not allowed.</span></span>

   ![허용되지 않는 외부 일정 공유를 표시하는 스크린샷.](../media/nocalendarsharing.png)

   <span data-ttu-id="9b1c8-359">다음 그림에서는 약속 있는/약속이 있는 정보만 있는 전자 메일 링크로 일정 공유가 허용되는 경우의 설정을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-359">The following figure shows the settings when calendar sharing is allowed with an email link with only free/busy information.</span></span>

   ![모든 사람과 약속이 있는 일정 공유의 스크린샷.](../media/sharefreebusy.png)

<span data-ttu-id="9b1c8-361">사용자가 일정을 공유할 수 있는 경우 [](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) 웹용 Outlook에서 공유하는 방법에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b1c8-361">If your users are allowed to share their calendars, see [these instructions](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for how to share from Outlook on the web.</span></span>
