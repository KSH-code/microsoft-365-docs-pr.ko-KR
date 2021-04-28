---
title: Outlook에서 가짓 긍정 및 거짓 부정 보고
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Outlook에서 가짓 긍정 및 거짓 부정을 보고하고 보고서 메시지 및 피싱 보고 추가 기능을 사용하도록 설정하는 방법을 학습합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065209"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="d9b7d-103">Outlook에서 가짓 긍정 및 거짓 부정 보고</span><span class="sxs-lookup"><span data-stu-id="d9b7d-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d9b7d-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-104">**Applies to**</span></span>
- [<span data-ttu-id="d9b7d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d9b7d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d9b7d-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="d9b7d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d9b7d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9b7d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="d9b7d-108">Exchange Online 사서함이 있는 Microsoft 365 조직의 관리자인 경우 보안 및 준수 센터의 제출 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="d9b7d-109">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="d9b7d-110">하이브리드 최신 인증을 사용하는 사서함이 있는 Microsoft 365 조직 또는 하이브리드 최신 인증을 사용하는 Microsoft 365 조직에서는 가음성(스팸으로 표시된 양호한 전자 메일) 및 거짓 부정(잘못된 전자 메일 및 피싱 허용)을 EOP(Exchange Online Protection)에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="d9b7d-111">보고서 메시지 기능을 사용하기 전에 기억해야 할 것</span><span class="sxs-lookup"><span data-stu-id="d9b7d-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="d9b7d-112">최상의 사용자 제출 환경을 위해 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="d9b7d-113">이 추가 기능의 작동 방식은 웹, iOS, Android 및 데스크톱 등 모든 플랫폼에서 Outlook에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="d9b7d-114">Exchange Online 사서함이 있는 조직의 관리자인 경우 보안 및 준수 센터의 제출 포털을 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="d9b7d-115">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="d9b7d-116">메시지를 Microsoft로 직접 보내거나 지정한 사서함 또는 둘 다로 보내도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="d9b7d-117">자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="d9b7d-118">Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="d9b7d-119">보고서 메시지 기능 사용</span><span class="sxs-lookup"><span data-stu-id="d9b7d-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="d9b7d-120">정크 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="d9b7d-120">Report junk and phishing messages</span></span>

<span data-ttu-id="d9b7d-121">받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더에 있는 메시지의 경우 다음 방법을 사용하여 스팸 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="d9b7d-122">선택한 **메시지의** 오른쪽 위에 있는 추가 작업 줄임표를  클릭하고 드롭다운 메뉴에서 메시지  보고를 클릭한 다음 정크 또는 피싱 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9b7d-123">![보고서 메시지 - 추가 작업](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9b7d-124">![보고서 메시지 - 정크 및 피싱](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="d9b7d-125">선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="d9b7d-126">스팸으로 보고된 경우 정크 메일 폴더로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="d9b7d-127">피싱으로 보고된 경우 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="d9b7d-128">정크 메일이 아닌 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="d9b7d-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="d9b7d-129">선택한 **메시지의** 오른쪽 위 모서리에 있는 추가 작업 줄임표를 클릭하고 드롭다운 메뉴에서 메시지 보고를 클릭한 다음 정크 메일 아님 **을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="d9b7d-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9b7d-130">![보고서 메시지 - 추가 작업](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9b7d-131">![보고서 메시지 - 정크 메일 아님](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="d9b7d-132">선택한 메시지가 분석을 위해 Microsoft로 전송되어 받은 편지함 또는 기타 지정된 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="d9b7d-133">보고서 메시지 및 피싱 보고 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="d9b7d-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="d9b7d-134">Outlook 및 웹용 Outlook(이전의 Outlook Web App)에 대한 피싱 보고 추가 기능을 사용하면 사용자가 분석을 위해 Microsoft 및 계열사에 가음성(나쁜 것으로 표시된 양호한 전자 메일) 또는 거짓 부정(잘못된 전자 메일 허용)을 쉽게 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="d9b7d-135">Microsoft는 이러한 제출을 사용하여 전자 메일 보호 기술의 효율성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="d9b7d-136">예를 들어 피싱 보고 추가 기능을 사용하여 많은 메시지를 보고하는 사람이 많은 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="d9b7d-137">이 정보는 보안 대시보드 및 기타 보고서에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="d9b7d-138">조직의 보안 팀은 이 정보를 피싱 방지 정책을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="d9b7d-139">보고서 메시지 또는 피싱 보고 추가 기능을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="d9b7d-140">사용자가 스팸 및 피싱 메시지를 모두 보고하게 하려는 경우 조직에 보고서 메시지 추가 기능을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="d9b7d-141">자세한 내용은 Enable the Report Message add-in을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="d9b7d-142">보고서 메시지 추가 기능은 스팸 및 피싱 메시지를 모두 보고하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="d9b7d-143">관리자는 조직에 대해 보고서 메시지 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="d9b7d-144">피싱 보고 추가 기능은 피싱 메시지만 보고하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="d9b7d-145">관리자는 조직에 대해 피싱 보고 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="d9b7d-146">개별 사용자인 경우 추가 기능을 모두 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="d9b7d-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="d9b7d-148">이제 중앙 집중식 배포를 통해 두 추가 [기능을 모두 사용할 수 있습니다.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d9b7d-149">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="d9b7d-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d9b7d-150">보고서 메시지 추가 기능 및 피싱 보고 추가 기능 모두 대부분의 Microsoft 365 구독 및 다음 제품과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="d9b7d-151">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b7d-151">Outlook on the web</span></span>
  - <span data-ttu-id="d9b7d-152">Outlook 2013 SP1 이상</span><span class="sxs-lookup"><span data-stu-id="d9b7d-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="d9b7d-153">Mac용 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9b7d-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="d9b7d-154">엔터프라이즈용 Microsoft 365 앱에 포함된 Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b7d-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="d9b7d-155">iOS 및 Android용 Outlook 앱</span><span class="sxs-lookup"><span data-stu-id="d9b7d-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="d9b7d-156">두 추가 기능을 모두 공유 사서함 또는 사내 Exchange 조직의 사서함에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="d9b7d-157">기존 웹 브라우저는 보고서 메시지와 피싱 보고 추가 기능 둘 다에서 작동해야 합니다. 그러나 추가 기능을 사용할 수 없는 경우 또는 예상대로 작동하지 않는 경우 다른 브라우저를 사용해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="d9b7d-158">조직 설치의 경우 OAuth 인증을 사용하도록 조직을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="d9b7d-159">자세한 내용은 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조하세요.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="d9b7d-160">관리자는 전역 관리자 역할 그룹의 구성원이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="d9b7d-161">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="d9b7d-162">보고서 메시지 추가 기능 확인</span><span class="sxs-lookup"><span data-stu-id="d9b7d-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="d9b7d-163">직접 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="d9b7d-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="d9b7d-164">에서 Microsoft AppSource로 이동하여 보고서 메시지 추가 기능을 <https://appsource.microsoft.com/marketplace/apps> 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="d9b7d-165">보고서 메시지 추가 기능으로 직접 이동하기 위해 로 <https://appsource.microsoft.com/product/office/wa104381180> 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="d9b7d-166">지금 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-166">Click **GET IT NOW**.</span></span>

   ![보고서 메시지 - 지금 시작](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="d9b7d-168">나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="d9b7d-169">직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="d9b7d-170">추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="d9b7d-171">Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="d9b7d-172">![Outlook용 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="d9b7d-173">웹에서 Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="d9b7d-174">![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="d9b7d-175">조직에 대한 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="d9b7d-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="d9b7d-176">추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="d9b7d-177">Microsoft 365 관리 센터에서 의 설정  추가 기능 페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="d9b7d-178">추가 기능 페이지가  없는 경우 통합 앱  페이지 맨 위에 있는 설정 통합 앱 추가 기능 \>  \>  **링크로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="d9b7d-179">페이지 **맨** 위에 있는 추가 기능 배포를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="d9b7d-181">새 **추가 기능** 배포 플라이아웃이 나타나면 정보를 검토하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="d9b7d-182">다음 페이지에서 **스토어에서 선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-182">On the next page, click **Choose from the Store**.</span></span>

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="d9b7d-184">나타나는 **추가 기능** 선택 페이지에서 검색 상자를 **클릭하고** 보고서 **메시지** 를 입력한 다음 검색 검색 아이콘 **을** ![ ](../../media/search-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="d9b7d-185">결과 목록에서 보고서 **메시지를 찾은 다음** 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![추가 기능 검색 결과 선택](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="d9b7d-187">나타나는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="d9b7d-188">나타나는 **추가 기능 구성** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d9b7d-189">**할당된 사용자:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="d9b7d-190">**모든** 사용자(기본값)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="d9b7d-191">**특정 사용자/그룹**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="d9b7d-192">**저뿐이에요**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-192">**Just me**</span></span>

   - <span data-ttu-id="d9b7d-193">**배포 방법:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="d9b7d-194">**고정(기본값)**: 추가 기능은 지정된 사용자에게 자동으로 배포되며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="d9b7d-195">**사용** 가능: 사용자는 홈 추가  기능 추가 기능 관리자가 관리하는 에서 추가 기능을 설치할 \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="d9b7d-196">**선택** 사항: 추가 기능을 지정된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![추가 기능 페이지 구성](../../media/configure-add-in.png)

   <span data-ttu-id="d9b7d-198">완료되면 배포를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="d9b7d-199">보고서 **메시지** 배포 페이지에 나타나는 진행률 보고서와 추가 기능 배포 확인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="d9b7d-200">정보를 읽은 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-200">After you read the information, click **Next**.</span></span>

   ![보고서 메시지 배포 페이지](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="d9b7d-202">추가 기능 발표 **페이지가** 나타나면 정보를 검토하고 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![추가 기능 페이지 발표](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="d9b7d-204">보고서 메시지 추가 기능의 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="d9b7d-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="d9b7d-205">Microsoft 365 관리 센터에서 의 설정  추가 기능 페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="d9b7d-206">추가 기능 페이지가  없는 경우 통합 앱  페이지 맨 위에 있는 설정 통합 앱 추가 기능 \>  \>  **링크로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![새 Add-Ins Microsoft 365 관리 센터의 서비스 및 서비스 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="d9b7d-208">보고서 메시지 **추가** 기능을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="d9b7d-209">보고서 **메시지 편집** 플라이아웃이 나타나면 조직에 적합한 설정을 검토하고 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="d9b7d-210">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-210">When you're finished, click **Save**.</span></span>

   ![보고서 메시지 추가 기능 설정](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="d9b7d-212">피싱 보고서 추가 기능 얻기</span><span class="sxs-lookup"><span data-stu-id="d9b7d-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="d9b7d-213">직접 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="d9b7d-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="d9b7d-214">에서 Microsoft AppSource로 이동하여 피싱 보고 추가 <https://appsource.microsoft.com/marketplace/apps> 기능을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="d9b7d-215">지금 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="d9b7d-216">나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="d9b7d-217">직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="d9b7d-218">추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="d9b7d-219">Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-219">In Outlook, the icon looks like this:</span></span>

  ![Outlook용 피싱 추가 기능 아이콘 보고](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="d9b7d-221">웹에서 Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="d9b7d-222">![웹용 Outlook 보고서 피싱 추가 기능 아이콘](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="d9b7d-223">조직에 대한 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="d9b7d-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="d9b7d-224">추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="d9b7d-225">Microsoft 365 관리 센터에서 의 설정  추가 기능 페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="d9b7d-226">추가 기능 페이지가  없는 경우 통합 앱  페이지 맨 위에 있는 설정 통합 앱 추가 기능 \>  \>  **링크로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="d9b7d-227">페이지 **맨** 위에 있는 추가 기능 배포를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="d9b7d-229">새 **추가 기능** 배포 플라이아웃이 나타나면 정보를 검토하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="d9b7d-230">다음 페이지에서 **스토어에서 선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-230">On the next page, click **Choose from the Store**.</span></span>

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="d9b7d-232">나타나는 **추가 기능** 선택 페이지에서 검색 상자를 **클릭하고** 피싱 **보고를** 입력한 다음 검색 **검색** 아이콘 을 ![ ](../../media/search-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="d9b7d-233">결과 목록에서 피싱 **보고를 찾은** 다음 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="d9b7d-234">나타나는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="d9b7d-235">나타나는 **추가 기능 구성** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d9b7d-236">**할당된 사용자:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="d9b7d-237">**모든** 사용자(기본값)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="d9b7d-238">**특정 사용자/그룹**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="d9b7d-239">**저뿐이에요**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-239">**Just me**</span></span>

   - <span data-ttu-id="d9b7d-240">**배포 방법:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="d9b7d-241">**고정(기본값)**: 추가 기능은 지정된 사용자에게 자동으로 배포되며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="d9b7d-242">**사용** 가능: 사용자는 홈 추가  기능 추가 기능 관리자가 관리하는 에서 추가 기능을 설치할 \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="d9b7d-243">**선택** 사항: 추가 기능을 지정된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="d9b7d-244">완료되면 배포를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="d9b7d-245">보고서 **피싱** 배포 페이지에 나타나는 진행률 보고서와 추가 기능 배포 확인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="d9b7d-246">정보를 읽은 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="d9b7d-247">추가 기능 발표 **페이지가** 나타나면 정보를 검토하고 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="d9b7d-248">피싱 보고 추가 기능 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="d9b7d-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="d9b7d-249">Microsoft 365 관리 센터에서 의 설정  추가 기능 페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="d9b7d-250">추가 기능 페이지가  없는 경우 통합 앱  페이지 맨 위에 있는 설정 통합 앱 추가 기능 \>  \>  **링크로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b7d-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="d9b7d-251">피싱 **보고 추가** 기능을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="d9b7d-252">조직에 **적합한** 설정이 나타나는 피싱 보고서 편집 플라이아웃에서 설정을 검토하고 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="d9b7d-253">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="d9b7d-254">보고된 메시지 보기 및 검토</span><span class="sxs-lookup"><span data-stu-id="d9b7d-254">View and review reported messages</span></span>

<span data-ttu-id="d9b7d-255">사용자가 Microsoft에 보고하는 메시지를 검토할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="d9b7d-256">관리 제출 포털을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="d9b7d-257">자세한 내용은 [Microsoft에 대한 사용자 제출 보기를 참조하세요.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="d9b7d-258">메일 흐름 규칙(전송 규칙)을 만들어 보고된 메시지의 복사본을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="d9b7d-259">자세한 내용은 메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고하는 것을 [참조하세요.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>