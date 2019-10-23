---
title: Microsoft 365 Business에 대 한 위협 요소 보호 강화
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection을 설정 하 고 중요 한 데이터를 보호 합니다.
ms.openlocfilehash: fb63ca7e3cf38ecf31aab98e425b02e8b9983bf8
ms.sourcegitcommit: 4d5e4cb3fa3ab45ad15f103c720c77277b22fc23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "37636755"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="d9f23-103">위협 방지 강화</span><span class="sxs-lookup"><span data-stu-id="d9f23-103">Increase threat protection</span></span>

<span data-ttu-id="d9f23-104">이 문서는 Microsoft 365 구독의 보호를 향상 시켜 피싱, 맬웨어 및 기타 위협 으로부터 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="d9f23-105">이러한 권장 사항은 법률 사무소 및 의료 보험 clinics 같은 보안 요구 사항이 증가 하는 조직에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-105">These recommendations are appropriate for organizations with an increased need for security, like law offices, and health care clinics.</span></span>

<span data-ttu-id="d9f23-106">시작 하기 전에 Office 365 보안 점수를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="d9f23-107">Office 365 안전한 점수는 일반 활동 및 보안 설정에 따라 Office 365 조직의 보안을 분석 하 고 점수를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-107">Office 365 Secure Score analyzes your Office 365 organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="d9f23-108">먼저 현재 점수를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="d9f23-109">이 문서에서 권장 하는 작업을 수행 하면 점수가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="d9f23-110">목표는 최대 점수를 얻는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호 하기 위한 기회를 확보 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-110">The goal is not to achieve the max score, but to be aware of opportunities to protect your environment that do not negatively affect productivity for your users.</span></span> 

<span data-ttu-id="d9f23-111">자세한 내용은 [Microsoft 보안 점수](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="d9f23-112">메일에서 맬웨어에 대 한 보호 수준 올리기</span><span class="sxs-lookup"><span data-stu-id="d9f23-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="d9f23-113">Office 365 또는 Microsoft 365 환경에는 맬웨어에 대 한 보호 기능이 포함 되어 있지만 일반적으로 맬웨어에 사용 되는 파일 형식을 사용 하 여 첨부 파일이 차단 되므로이 보호 기능을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="d9f23-114">전자 메일에서 맬웨어 보호를 강화 하려면:</span><span class="sxs-lookup"><span data-stu-id="d9f23-114">To increase malware protection in email:</span></span>
  
1. <span data-ttu-id="d9f23-115">으로 이동 [https://protection.office.com](https://protection.office.com) 하 고 관리자 계정 자격 증명으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-115">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span> 
    
2. <span data-ttu-id="d9f23-116">Office 365 보안 &amp; 및 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책** \> **맬웨어 방지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-116">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>
    
3. <span data-ttu-id="d9f23-117">기본 정책을 두 번 클릭 하 여이 회사 차원의 정책을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-117">Double-click the default policy to edit this company-wide policy.</span></span>
    
4. <span data-ttu-id="d9f23-118">**설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-118">Click **Settings**.</span></span>
    
5. <span data-ttu-id="d9f23-119">**일반 첨부 파일 형식 필터**에서 **설정**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="d9f23-120">차단 되는 파일 형식은이 컨트롤 바로 아래의 창에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-120">The file types that are blocked are listed in the window directly below this control.</span></span>  <span data-ttu-id="d9f23-121">다음 filetypes를 추가 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-121">Make sure you add these filetypes:</span></span>
   - <span data-ttu-id="d9f23-122">ade, adp, ani, bas, bat, chm, cmd, a, m, s, com, cpl, crt, .hlp, ht, mdz, inf, v p v, ini, 작업, js, shs, 모바일,, mde, msi, wsc, .pcd, s p l, exe, .wsf 인</span><span class="sxs-lookup"><span data-stu-id="d9f23-122">ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif</span></span>  <br/> <span data-ttu-id="d9f23-123">필요한 경우 나중에 파일 형식을 추가 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-123">You can add or delete file types later, if needed.</span></span>
    
6. <span data-ttu-id="d9f23-124">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-124">Click **Save.**</span></span>
    
<span data-ttu-id="d9f23-125">자세한 내용은 [맬웨어 방지 보호](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-125">For more information, see [Anti-malware protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).</span></span>
  
## <a name="protect-against-ransomware"></a><span data-ttu-id="d9f23-126">랜 섬 웨어 로부터 보호</span><span class="sxs-lookup"><span data-stu-id="d9f23-126">Protect against ransomware</span></span>

<span data-ttu-id="d9f23-127">랜 섬 웨어는 파일 암호화 또는 컴퓨터 화면 잠금을 통해 데이터에 대 한 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="d9f23-128">그런 다음 "ransom"를 사용 하 여 victims에서 데이터에 액세스 하는 데 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-128">It then attempts to extort money from victims by asking for "ransom," usually in form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span> 
  
<span data-ttu-id="d9f23-129">메일 흐름 규칙을 하나 이상 만들어, 차단에 일반적으로 사용 되는 파일 확장명 (예를 들어, mail 단계에서 맬웨어에 대 한 [보호 수준 올리기](#raise-the-level-of-protection-against-malware-in-mail) )을 중단 하거나 이러한 메시지를 받는 사용자에 게 경고 합니다. 전자 메일의 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="d9f23-129">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="d9f23-130">이전 단계에서 차단한 파일 외에도 매크로를 포함 하는 Office 첨부 파일을 열기 전에 사용자에 게 경고 하는 규칙을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-130">In addition to the files that you blocked in the previous step, it is also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="d9f23-131">매크로를 사용할 수 없도록이 파일을 사용자에 게 경고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-131">Ransomware can be hidden inside macros, so we'll warn users to not open these files from people they do not know.</span></span>

<span data-ttu-id="d9f23-132">메일 전송 규칙을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-132">To create a mail transport rule:</span></span>
  
1. <span data-ttu-id="d9f23-133">관리 센터로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 하 여 **관리 센터** \> **Exchange**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-133">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="d9f23-134">**메일 흐름** 범주에서 **규칙**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-134">In the **mail flow** category, click **rules**.</span></span>
    
3. <span data-ttu-id="d9f23-135">을 **+** 클릭 한 다음 **새 규칙 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-135">Click **+**, and then click **Create a new rule**.</span></span>
    
4. <span data-ttu-id="d9f23-136">대화 상자 아래쪽에 있는 **기타 옵션** 을 클릭 하 여 전체 옵션 집합을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-136">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="d9f23-137">다음 표에 해당 규칙에 대 한 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-137">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="d9f23-138">설정을 변경 하려는 경우가 아니면 나머지 설정은 기본값으로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-138">Leave the rest of the settings at the default, unless you want to change these.</span></span>
    
6. <span data-ttu-id="d9f23-139">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-139">Click **Save**.</span></span>
    
|<span data-ttu-id="d9f23-140">**설정**</span><span class="sxs-lookup"><span data-stu-id="d9f23-140">**Setting**</span></span>|<span data-ttu-id="d9f23-141">**Office 파일의 첨부 파일을 열기 전에 사용자에 게 경고 표시**</span><span class="sxs-lookup"><span data-stu-id="d9f23-141">**Warn users before opening attachments of Office files**</span></span>||
|:-----|:-----|:-----|
|<span data-ttu-id="d9f23-142">Name</span><span class="sxs-lookup"><span data-stu-id="d9f23-142">Name</span></span>  <br/> |<span data-ttu-id="d9f23-143">랜 섬 웨어 방지 규칙: 사용자에 게 경고 표시</span><span class="sxs-lookup"><span data-stu-id="d9f23-143">Anti-ransomware rule: warn users</span></span>  <br/>  |
|<span data-ttu-id="d9f23-144">다음 경우에이 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-144">Apply this rule if .</span></span> <span data-ttu-id="d9f23-145">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-145"></span></span> <span data-ttu-id="d9f23-146">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-146"></span></span>  <br/> |<span data-ttu-id="d9f23-147">모든 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="d9f23-147">Any attachment .</span></span> <span data-ttu-id="d9f23-148">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-148"></span></span> <span data-ttu-id="d9f23-149">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-149"></span></span> <span data-ttu-id="d9f23-150">일치 하는 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="d9f23-150">file extension matches .</span></span> <span data-ttu-id="d9f23-151">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-151"></span></span> <span data-ttu-id="d9f23-152">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-152"></span></span>  <br/> |
|<span data-ttu-id="d9f23-153">단어 또는 구 지정</span><span class="sxs-lookup"><span data-stu-id="d9f23-153">Specify words or phrases</span></span>  <br/> |<span data-ttu-id="d9f23-154">다음 파일 형식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-154">Add these file types:</span></span>  <br/> <span data-ttu-id="d9f23-155">normal.dotm, .docm, .xlsm, sltm, .xla, xlam, xll, pptm, potm, ppam, ppsm, sltm</span><span class="sxs-lookup"><span data-stu-id="d9f23-155">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>  <br/>|
|<span data-ttu-id="d9f23-156">다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-156">Do the following .</span></span> <span data-ttu-id="d9f23-157">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-157"></span></span> <span data-ttu-id="d9f23-158">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-158"></span></span>  <br/> |<span data-ttu-id="d9f23-159">받는 사람에게 메시지로 알림</span><span class="sxs-lookup"><span data-stu-id="d9f23-159">Notify the recipient with a message</span></span>  <br/> |
|<span data-ttu-id="d9f23-160">메시지 텍스트 제공</span><span class="sxs-lookup"><span data-stu-id="d9f23-160">Provide message text</span></span>  <br/> |<span data-ttu-id="d9f23-161">악성 코드가 포함 된 매크로를 포함할 수 있으므로 모르는 사용자 로부터 이러한 유형의 파일을 열지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d9f23-161">Do not open these type of files from people you do not know because they might contain macros with malicious code.</span></span>  <br/> |
   
<span data-ttu-id="d9f23-162">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-162">For more information, see:</span></span>
  
- [<span data-ttu-id="d9f23-163">랜 섬 웨어를 처리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="d9f23-163">How to deal with ransomware</span></span>](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [<span data-ttu-id="d9f23-164">OneDrive 복원</span><span class="sxs-lookup"><span data-stu-id="d9f23-164">Restore your OneDrive</span></span>](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="d9f23-165">전자 메일에 대 한 자동 전달 중지</span><span class="sxs-lookup"><span data-stu-id="d9f23-165">Stop auto-forwarding for email</span></span>

<span data-ttu-id="d9f23-166">사용자의 사서함에 대 한 액세스 권한을 획득 하는 해커는 전자 메일을 자동으로 전달 하도록 사서함을 설정 하 여 메일을 도용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-166">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="d9f23-167">사용자의 인식이 없어도이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-167">This can happen even without the user's awareness.</span></span> <span data-ttu-id="d9f23-168">메일 흐름 규칙을 구성 하 여 이러한 상황이 발생 하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-168">You can prevent this from happening by configuring a mail flow rule.</span></span> 
  
<span data-ttu-id="d9f23-169">메일 전송 규칙을 만들려면 [이 짧은 비디오](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) 를 시청 하거나 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-169">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>
  
1. <span data-ttu-id="d9f23-170">Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-170">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="d9f23-171">**메일 흐름** 범주에서 **규칙**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-171">In the **mail flow** category, click **rules**.</span></span>
    
3. <span data-ttu-id="d9f23-172">을 **+** 클릭 한 다음 **새 규칙 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-172">Click **+**, and then click **Create a new rule**.</span></span>
    
4. <span data-ttu-id="d9f23-173">대화 상자 아래쪽에 있는 **기타 옵션** 을 클릭 하 여 전체 옵션 집합을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-173">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="d9f23-174">다음 표의 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-174">Apply the settings in the following table.</span></span> <span data-ttu-id="d9f23-175">설정을 변경 하려는 경우가 아니면 나머지 설정은 기본값으로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-175">Leave the rest of the settings at the default, unless you want to change these.</span></span>
    
6. <span data-ttu-id="d9f23-176">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-176">Click **Save**.</span></span>
    
|<span data-ttu-id="d9f23-177">**설정**</span><span class="sxs-lookup"><span data-stu-id="d9f23-177">**Setting**</span></span>|<span data-ttu-id="d9f23-178">**Office 파일의 첨부 파일을 열기 전에 사용자에 게 경고 표시**</span><span class="sxs-lookup"><span data-stu-id="d9f23-178">**Warn users before opening attachments of Office files**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9f23-179">Name</span><span class="sxs-lookup"><span data-stu-id="d9f23-179">Name</span></span>  <br/> |<span data-ttu-id="d9f23-180">외부 도메인에 대 한 전자 메일 자동 전달 금지</span><span class="sxs-lookup"><span data-stu-id="d9f23-180">Prevent auto forwarding of email to external domains</span></span>  <br/> |
|<span data-ttu-id="d9f23-181">다음 경우에이 규칙 적용 ...</span><span class="sxs-lookup"><span data-stu-id="d9f23-181">Apply this rule if ...</span></span>  <br/> |<span data-ttu-id="d9f23-182">보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-182">The sender .</span></span> <span data-ttu-id="d9f23-183">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-183"></span></span> <span data-ttu-id="d9f23-184">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-184"></span></span> <span data-ttu-id="d9f23-185">은 외부/내부입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-185">is external/internal .</span></span> <span data-ttu-id="d9f23-186">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-186"></span></span> <span data-ttu-id="d9f23-187">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-187"></span></span> <span data-ttu-id="d9f23-188">조직 내부</span><span class="sxs-lookup"><span data-stu-id="d9f23-188">Inside the organization</span></span>  <br/> |
|<span data-ttu-id="d9f23-189">조건 추가</span><span class="sxs-lookup"><span data-stu-id="d9f23-189">Add condition</span></span>  <br/> |<span data-ttu-id="d9f23-190">메시지 속성</span><span class="sxs-lookup"><span data-stu-id="d9f23-190">The message properties .</span></span> <span data-ttu-id="d9f23-191">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-191"></span></span> <span data-ttu-id="d9f23-192">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-192"></span></span> <span data-ttu-id="d9f23-193">메시지 유형을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-193">include the message type .</span></span> <span data-ttu-id="d9f23-194">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-194"></span></span> <span data-ttu-id="d9f23-195">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-195"></span></span> <span data-ttu-id="d9f23-196">자동 전달</span><span class="sxs-lookup"><span data-stu-id="d9f23-196">Auto-forward</span></span>  <br/> |
|<span data-ttu-id="d9f23-197">다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-197">Do the following ...</span></span>  <br/> |<span data-ttu-id="d9f23-198">메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-198">Block the message .</span></span> <span data-ttu-id="d9f23-199">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-199"></span></span> <span data-ttu-id="d9f23-200">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-200"></span></span> <span data-ttu-id="d9f23-201">메시지를 거부 하 고 설명을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-201">reject the message and include an explanation.</span></span>  <br/> |
|<span data-ttu-id="d9f23-202">메시지 텍스트 제공</span><span class="sxs-lookup"><span data-stu-id="d9f23-202">Provide message text</span></span>  <br/> |<span data-ttu-id="d9f23-203">보안상의 이유로이 조직 외부에서 전자 메일을 자동 전달 하는 것은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-203">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="d9f23-204">피싱 공격 으로부터 전자 메일을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-204">Protect your email from phishing attacks</span></span>

<span data-ttu-id="d9f23-205">Office 365 또는 Microsoft 365 환경용으로 하나 이상의 사용자 지정 도메인을 구성한 경우 대상 피싱 방지 보호 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-205">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="d9f23-206">ATP 피싱 방지 보호, Office 365 Advanced Threat Protection의 일부분은 악의적인 가장 기반 피싱 공격과 기타 피싱 공격 으로부터 조직을 보호 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-206">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="d9f23-207">사용자 지정 도메인을 구성 하지 않은 경우에는이 작업을 수행 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-207">If you haven't configured a custom domain, you do not need to do this.</span></span>
  
<span data-ttu-id="d9f23-208">가장 중요 한 사용자와 사용자 지정 도메인을 보호 하는 정책을 만들어이 보호를 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-208">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span> 

  
<span data-ttu-id="d9f23-209">ATP 피싱 방지 정책을 만들려면 [이 간략 한 교육 비디오](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)를 시청 하거나 다음 단계를 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-209">To create an ATP anti-phishing policy, watch  [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>
  
1. <span data-ttu-id="d9f23-210">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-210">Go to [https://protection.office.com](https://protection.office.com).</span></span> 
    
2. <span data-ttu-id="d9f23-211">Office 365 보안 &amp; 및 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-211">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="d9f23-212">**정책** 페이지에서 **ATP 피싱 방지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-212">On the **Policy** page, choose **ATP anti-phishing**.</span></span>
    
4. <span data-ttu-id="d9f23-213">**피싱 방지** 페이지에서 **+ 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-213">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="d9f23-214">피싱 방지 정책을 정의 하는 과정을 안내 하는 마법사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-214">A wizard launches that steps you through defining your anti-phishing policy.</span></span>
    
5. <span data-ttu-id="d9f23-215">아래 차트에서 권장 하는 대로 정책에 대 한 이름, 설명 및 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-215">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="d9f23-216">자세한 내용은 [ATP 피싱 방지 정책 옵션에 대 한](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options) 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-216">See [Learn about ATP anti-phishing policy options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options) for more details.</span></span> 
    
6. <span data-ttu-id="d9f23-217">설정을 검토 한 후에는 **이 정책 만들기** 또는 적절 한 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-217">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="d9f23-218">**설정 또는 옵션**</span><span class="sxs-lookup"><span data-stu-id="d9f23-218">**Setting or option**</span></span><br/>|<span data-ttu-id="d9f23-219">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="d9f23-219">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="d9f23-220">Name</span><span class="sxs-lookup"><span data-stu-id="d9f23-220">Name</span></span>  <br/> |<span data-ttu-id="d9f23-221">도메인 및 가장 귀중 한 캠페인 직원</span><span class="sxs-lookup"><span data-stu-id="d9f23-221">Domain and most valuable campaign staff</span></span>  <br/> |
|<span data-ttu-id="d9f23-222">설명</span><span class="sxs-lookup"><span data-stu-id="d9f23-222">Description</span></span>  <br/> |<span data-ttu-id="d9f23-223">가장 중요 한 직원과 해당 도메인이 가장 되 고 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-223">Ensure most important staff and our domain are not being impersonated.</span></span>  <br/> |
|<span data-ttu-id="d9f23-224">보호할 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="d9f23-224">Add users to protect</span></span>  <br/> |<span data-ttu-id="d9f23-225">**조건을 추가 하 고 받는 사람**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-225">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="d9f23-226">사용자 이름을 입력 하거나 후보, 캠페인 관리자 및 기타 중요 교직원 구성원의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-226">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="d9f23-227">가장을 보호 하려는 최대 20 개의 내부 및 외부 주소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-227">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>  <br/> |
|<span data-ttu-id="d9f23-228">보호할 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="d9f23-228">Add domains to protect</span></span>  <br/> |<span data-ttu-id="d9f23-229">**조건 추가, 받는 사람 도메인**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-229">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="d9f23-230">Microsoft 365 구독에 연결 된 사용자 지정 도메인 (하나를 정의한 경우)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-230">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="d9f23-231">둘 이상의 도메인을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-231">You can enter more than one domain.</span></span>  <br/> |
|<span data-ttu-id="d9f23-232">작업 선택</span><span class="sxs-lookup"><span data-stu-id="d9f23-232">Choose actions</span></span>  <br/> |<span data-ttu-id="d9f23-233">가장 된 사용자가 전자 메일을 보낸 경우: **다른 전자 메일 주소로 메시지 리디렉션을**선택 하 고 보안 관리자의 전자 메일 주소를 입력 합니다. 예를 들어 *Alice<span><span>@contoso 합니다.*</span><span class="sxs-lookup"><span data-stu-id="d9f23-233">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span>          <span data-ttu-id="d9f23-234">가장 된 도메인에서 전자 메일을 보낸 경우에는 **격리 메시지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-234">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>  <br/> |
|<span data-ttu-id="d9f23-235">사서함 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="d9f23-235">Mailbox intelligence</span></span>  <br/> |<span data-ttu-id="d9f23-236">기본적으로 새 피싱 방지 정책을 만들 때 사서함 인텔리전스가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-236">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="d9f23-237">최상의 결과를 **위해이 설정을 유지 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9f23-237">Leave this setting **On** for best results.</span></span>  <br/> |
|<span data-ttu-id="d9f23-238">신뢰할 수 있는 보낸 사람 및 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="d9f23-238">Add trusted senders and domains</span></span>  <br/> |<span data-ttu-id="d9f23-239">여기에서 자체 도메인 또는 다른 트러스트 된 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-239">Here you can add your own domain, or any other trusted domains.</span></span>  <br/> |
|<span data-ttu-id="d9f23-240">적용 대상</span><span class="sxs-lookup"><span data-stu-id="d9f23-240">Applied to</span></span>  <br/> |<span data-ttu-id="d9f23-241">**받는 사람 도메인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-241">Select **The recipient domain is**.</span></span> <span data-ttu-id="d9f23-242">**다음 중 하나**에서 **선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-242">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="d9f23-243">**+ 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-243">Select **+ Add**.</span></span> <span data-ttu-id="d9f23-244">도메인 이름 (예: contoso) 옆에 있는 확인란을 선택 합니다 *.<span> com <span>* 의 목록에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-244">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="d9f23-245">**완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-245">Select **Done**.</span></span>  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a><span data-ttu-id="d9f23-246">ATP 안전한 첨부 파일을 사용 하 여 악의 있는 첨부 파일과 파일을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-246">Protect against malicious attachments and files with ATP Safe Attachments</span></span>

<span data-ttu-id="d9f23-247">사용자가 문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-247">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="d9f23-248">전자 메일 메시지를 확인 하기만 하면 첨부 파일이 안전한 지 또는 악의적 임을 쉽게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-248">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="d9f23-249">Office 365 Advanced Threat Protection은 ATP Safe 첨부 파일 보호를 포함 하지만이 보호 기능은 기본적으로 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-249">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="d9f23-250">이 보호 기능을 사용 하기 시작 하는 새 규칙을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-250">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="d9f23-251">이 보호는 SharePoint, OneDrive 및 Microsoft 팀의 파일로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-251">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>
  
<span data-ttu-id="d9f23-252">ATP 안전한 첨부 파일 정책을 만들려면 [이 짧은 비디오](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)를 시청 하거나 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-252">To create an ATP safe attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>
  
1. <span data-ttu-id="d9f23-253">으로 이동 [https://protection.office.com](https://protection.office.com) 하 고 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-253">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="d9f23-254">Office 365 보안 &amp; 및 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-254">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="d9f23-255">정책 페이지에서 **ATP 안전한 첨부 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-255">On the Policy page, choose **ATP safe attachments**.</span></span>
    
4. <span data-ttu-id="d9f23-256">안전한 첨부 파일 페이지에서 **SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP 설정** 확인란을 선택 하 여이 보호를 광범위 하 게 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-256">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span> 
    
5. <span data-ttu-id="d9f23-257">새 **+** 정책을 만들려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-257">Select **+** to create a new policy.</span></span> 
    
6. <span data-ttu-id="d9f23-258">다음 표의 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-258">Apply the settings in the following table.</span></span> 
    
7. <span data-ttu-id="d9f23-259">설정을 검토 한 후에는 **이 정책 만들기** 또는 적절 한 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-259">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="d9f23-260">**설정 또는 옵션**</span><span class="sxs-lookup"><span data-stu-id="d9f23-260">**Setting or option**</span></span>|<span data-ttu-id="d9f23-261">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="d9f23-261">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="d9f23-262">Name</span><span class="sxs-lookup"><span data-stu-id="d9f23-262">Name</span></span>  <br/> |<span data-ttu-id="d9f23-263">검색 된 맬웨어로부터 현재 및 향후 전자 메일을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-263">Block current and future emails with detected malware.</span></span>  <br/> |
|<span data-ttu-id="d9f23-264">설명</span><span class="sxs-lookup"><span data-stu-id="d9f23-264">Description</span></span>  <br/> |<span data-ttu-id="d9f23-265">검색 된 맬웨어로부터 현재 및 향후 전자 메일 및 첨부 파일을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-265">Block current and future emails and attachments with detected malware.</span></span>  <br/> |
|<span data-ttu-id="d9f23-266">첨부 파일 저장 알 수 없는 맬웨어 응답</span><span class="sxs-lookup"><span data-stu-id="d9f23-266">Save attachments unknown malware response</span></span>  <br/> |<span data-ttu-id="d9f23-267">차단 됨을 선택 하 고 **검색 된 맬웨어로부터 현재 및 앞으로의 전자 메일 및 첨부 파일을 차단**합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-267">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>  <br/> |
|<span data-ttu-id="d9f23-268">검색 시 첨부 파일 리디렉션</span><span class="sxs-lookup"><span data-stu-id="d9f23-268">Redirect attachment on detection</span></span>  <br/> |<span data-ttu-id="d9f23-269">리디렉션 사용 (이 상자를 선택 합니다.) 격리를 위해 관리자 계정 또는 사서함 설정을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-269">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="d9f23-270">첨부 파일에 대 한 맬웨어 검사 시간이 초과 되거나 오류가 발생 하면 (이 상자를 선택 하십시오.) 위의 선택 사항을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-270">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>  <br/> |
|<span data-ttu-id="d9f23-271">적용 대상</span><span class="sxs-lookup"><span data-stu-id="d9f23-271">Applied to</span></span>  <br/> |<span data-ttu-id="d9f23-272">받는 사람 도메인은입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-272">The recipient domain is .</span></span> <span data-ttu-id="d9f23-273">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-273"></span></span> <span data-ttu-id="d9f23-274">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-274"></span></span> <span data-ttu-id="d9f23-275">도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-275">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="d9f23-276">자세한 내용은 [Set Up Office 365 ATP 피싱 방지 정책](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-276">For more information, see [Set up Office 365 ATP anti-phishing policies](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).</span></span>
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a><span data-ttu-id="d9f23-277">ATP 안전한 링크를 통한 피싱 공격 으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="d9f23-277">Protect against phishing attacks with ATP Safe Links</span></span>

<span data-ttu-id="d9f23-278">해커는 전자 메일 이나 다른 파일의 링크에서 악성 웹 사이트를 숨기는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-278">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="d9f23-279">Office 365 ATP 안전한 링크 (ATP 안전한 링크)는 Office 365 Advanced Threat Protection의 일부 이며, 전자 메일 메시지 및 Office 문서에서 웹 주소 (Url)를 클릭 하 여 확인할 시간을 제공 하 여 조직을 보호 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-279">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="d9f23-280">보호는 ATP 안전한 링크 정책을 통해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-280">Protection is defined through ATP Safe Links policies.</span></span>
  
<span data-ttu-id="d9f23-281">다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-281">We recommend that you do the following:</span></span>
  
- <span data-ttu-id="d9f23-282">기본 정책을 수정 하 여 보호를 강화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-282">Modify the default policy to increase protection.</span></span>
    
- <span data-ttu-id="d9f23-283">도메인의 모든 받는 사람을 대상으로 하는 새 정책을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-283">Add a new policy targeted to all recipients in your domain.</span></span>
    
<span data-ttu-id="d9f23-284">ATP 안전한 링크를 설정 하려면 [이 간략 한 교육 비디오](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)를 시청 하거나 다음 단계를 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-284">To set up ATP Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>
  
1. <span data-ttu-id="d9f23-285">으로 이동 [https://protection.office.com](https://protection.office.com) 하 고 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-285">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="d9f23-286">Office 365 보안 &amp; 및 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-286">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="d9f23-287">정책 페이지에서 **ATP 안전한 링크**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-287">On the Policy page, choose **ATP Safe Links**.</span></span>
    
<span data-ttu-id="d9f23-288">기본 정책을 수정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-288">To modify the default policy:</span></span>
  
1. <span data-ttu-id="d9f23-289">안전한 링크 페이지의 **전체 조직에 적용 되는 정책**에서 **기본** 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-289">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span> 
    
2. <span data-ttu-id="d9f23-290">**전자 메일을 제외 하 고 콘텐츠에 적용 되는 설정**아래에서 **office 365 ProPlus, iOS 및 Android 용 office를 차례로**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-290">Under **Settings that apply to content except email**, select **Office 365 ProPlus, Office for iOS and Android**.</span></span>
    
3. <span data-ttu-id="d9f23-291">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-291">Click **Save**.</span></span> 
    
<span data-ttu-id="d9f23-292">도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-292">To create a new policy targeted to all recipients in your domain:</span></span>
  
1. <span data-ttu-id="d9f23-293">안전한 링크 페이지의 **전체 조직에 적용 되는 정책**에서를 클릭 **+** 하 여 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-293">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span> 
    
2. <span data-ttu-id="d9f23-294">다음 표에 나와 있는 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-294">Apply the settings listed in the following table.</span></span>
    
3. <span data-ttu-id="d9f23-295">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-295">Click **Save**.</span></span> 

|<span data-ttu-id="d9f23-296">**설정 또는 옵션**</span><span class="sxs-lookup"><span data-stu-id="d9f23-296">**Setting or option**</span></span>|<span data-ttu-id="d9f23-297">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="d9f23-297">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="d9f23-298">Name</span><span class="sxs-lookup"><span data-stu-id="d9f23-298">Name</span></span>  <br/> |<span data-ttu-id="d9f23-299">도메인의 모든 받는 사람에 대 한 안전한 링크 정책</span><span class="sxs-lookup"><span data-stu-id="d9f23-299">Safe links policy for all recipients in the domain</span></span>  <br/> |
|<span data-ttu-id="d9f23-300">메시지에서 알 수 없는 잠재적 악성 Url에 대 한 작업 선택</span><span class="sxs-lookup"><span data-stu-id="d9f23-300">Select the action for unknown potentially malicious URLs in messages</span></span>  <br/> |<span data-ttu-id="d9f23-301">**Url 선택-사용자가 링크를 클릭할 때 알려진 악성 링크 목록에 대해 다시 작성 및 확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-301">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>  <br/> |
|<span data-ttu-id="d9f23-302">다운로드 가능한 콘텐츠를 검색 하기 위해 안전한 첨부 파일 사용</span><span class="sxs-lookup"><span data-stu-id="d9f23-302">Use Safe Attachments to scan downloadable content</span></span>  <br/> |<span data-ttu-id="d9f23-303">이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-303">Select this box.</span></span>  <br/> |
|<span data-ttu-id="d9f23-304">적용 대상</span><span class="sxs-lookup"><span data-stu-id="d9f23-304">Applied to</span></span>  <br/> |<span data-ttu-id="d9f23-305">받는 사람 도메인은입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-305">The recipient domain is .</span></span> <span data-ttu-id="d9f23-306">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-306"></span></span> <span data-ttu-id="d9f23-307">.</span><span class="sxs-lookup"><span data-stu-id="d9f23-307"></span></span> <span data-ttu-id="d9f23-308">도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-308">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="d9f23-309">자세한 내용은 [Office 365 ATP 안전한 링크](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-309">For more information, see [Office 365 ATP safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="d9f23-310">Intune 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-310">Go to Intune admin center</span></span>

1. <span data-ttu-id="d9f23-311">[Azure Portal](https://portal.azure.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-311">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="d9f23-312">**모든 서비스**를 선택하고 **검색 상자**에 *Intune*을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-312">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="d9f23-313">결과가 표시되면 **Microsoft Intune** 옆에 있는 시작을 클릭하여 즐겨찾기로 지정하고 나중에 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-313">Once the results display, click the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="d9f23-314">관리 센터 외에도 Intune을 사용 하 여 조직의 장치를 등록 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f23-314">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="d9f23-315">자세한 내용은 [Windows 장치용 등록 방법](https://docs.microsoft.com/intune/enrollment-method-capabs) 및 [Intune으로 관리 되는 장치에 대 한 등록 옵션](https://docs.microsoft.com/intune/enrollment-options)의 기능을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f23-315">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>
