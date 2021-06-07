---
title: 보고서 메시지 또는 피싱 보고 추가 기능 사용
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 웹, 개별 사용자 또는 전체 조직에 대해 웹에서 Outlook Outlook 보고서 피싱 추가 기능 또는 보고서 피싱 추가 기능을 사용하도록 설정하는 방법을 학습합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 25c4f7d67fd4fa876544a17df0f4bc1abfd7b3e7
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782936"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="c3919-103">보고서 메시지 또는 피싱 보고 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="c3919-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3919-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="c3919-104">**Applies to**</span></span>
- [<span data-ttu-id="c3919-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c3919-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c3919-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="c3919-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c3919-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3919-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="c3919-108">사서함이 있는 Microsoft 365 조직의 관리자인 Exchange Online 보안 및 준수 센터의 제출 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c3919-109">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c3919-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c3919-110">웹에서 Outlook 및 Outlook(이전의 Outlook Web App)에 대한 피싱 보고 추가 기능을 사용하면 사용자가 분석을 위해 Microsoft 및 계열사에 가음성(나쁜 것으로 표시된 좋은 전자 메일) 또는 거짓 부정(잘못된 전자 메일 허용)을 쉽게 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="c3919-111">Microsoft는 이러한 제출을 사용하여 전자 메일 보호 기술의 효율성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="c3919-112">예를 들어 피싱 보고 추가 기능을 사용하여 많은 메시지를 보고하는 사람이 많은 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="c3919-113">이 정보는 보안 대시보드 및 기타 보고서에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="c3919-114">조직의 보안 팀은 이 정보를 피싱 방지 정책을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="c3919-115">보고서 메시지 또는 피싱 보고 추가 기능을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="c3919-116">사용자가 스팸 및 피싱 메시지를 모두 보고하게 하려는 경우 조직에 보고서 메시지 추가 기능을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="c3919-117">자세한 내용은 Enable the Report Message add-in을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3919-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="c3919-118">보고서 메시지 추가 기능은 스팸 및 피싱 메시지를 모두 보고하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="c3919-119">관리자는 조직에 대해 보고서 메시지 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="c3919-120">피싱 보고 추가 기능은 피싱 메시지만 보고하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="c3919-121">관리자는 조직에 대해 피싱 보고 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="c3919-122">개별 사용자인 경우 추가 기능을 모두 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="c3919-123">전역 관리자 또는 Exchange Online 관리자로서 Exchange OAuth 인증을 사용하도록 구성된 경우 조직에 대해 보고서 메시지 추가 기능 및 피싱 보고 추가 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="c3919-124">이제 중앙 집중식 배포를 통해 두 추가 [기능을 모두 사용할 수 있습니다.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="c3919-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3919-125">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c3919-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3919-126">보고서 메시지 추가 기능 및 피싱 보고 추가 기능 모두 대부분의 Microsoft 365 및 다음 제품과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="c3919-127">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="c3919-127">Outlook on the web</span></span>
  - <span data-ttu-id="c3919-128">Outlook 2013 SP1 이상</span><span class="sxs-lookup"><span data-stu-id="c3919-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="c3919-129">Mac용 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c3919-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="c3919-130">Outlook 앱용 Microsoft 365 포함된 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c3919-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="c3919-131">Outlook iOS 및 Android용 앱</span><span class="sxs-lookup"><span data-stu-id="c3919-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="c3919-132">두 추가 기능을 모두 공유 사서함 또는 조직에 있는 사서함에 사용할 Exchange 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="c3919-133">기존 웹 브라우저는 보고서 메시지와 피싱 보고 추가 기능 둘 다에서 작동해야 합니다. 그러나 추가 기능을 사용할 수 없는 경우 또는 예상대로 작동하지 않는 경우 다른 브라우저를 사용해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="c3919-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="c3919-134">조직 설치의 경우 OAuth 인증을 사용하도록 조직을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="c3919-135">자세한 내용은 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조하세요.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="c3919-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="c3919-136">관리자는 전역 관리자 역할 그룹의 구성원이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="c3919-137">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3919-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="c3919-138">보고서 메시지 기능을 사용하여 메시지를 보고하는 방법에 대한 자세한 내용은 report [false positives and false negatives in Outlook.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="c3919-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="c3919-139">보고서 메시지 추가 기능 확인</span><span class="sxs-lookup"><span data-stu-id="c3919-139">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="c3919-140">직접 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="c3919-140">Get the add-in for yourself</span></span>

1. <span data-ttu-id="c3919-141">에서 Microsoft AppSource로 이동하여 보고서 메시지 추가 기능을 <https://appsource.microsoft.com/marketplace/apps> 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-141">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="c3919-142">보고서 메시지 추가 기능으로 직접 이동하기 위해 로 <https://appsource.microsoft.com/product/office/wa104381180> 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3919-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="c3919-143">지금 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-143">Click **GET IT NOW**.</span></span>

   ![보고서 메시지 - 지금 시작](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="c3919-145">나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-145">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c3919-146">직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-146">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c3919-147">추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-147">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c3919-148">이 Outlook 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-148">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="c3919-149">![보고서 메시지 추가 기능 아이콘을 Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="c3919-149">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="c3919-150">웹 Outlook 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-150">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="c3919-151">![Outlook 보고서 메시지 추가 기능 아이콘에 표시됩니다.](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="c3919-151">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="c3919-152">조직에 대한 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="c3919-152">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c3919-153">추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-153">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c3919-154">Microsoft 365 관리 센터에서 의 설정 추가 기능  페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-154">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="c3919-155">추가 기능 페이지가  없는 경우 통합 앱 **페이지 설정** 통합 앱 추가 기능 링크로 \>  \>  이동합니다. </span><span class="sxs-lookup"><span data-stu-id="c3919-155">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c3919-156">페이지 **맨** 위에 있는 추가 기능 배포를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-156">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="c3919-158">새 **추가 기능** 배포 플라이아웃이 나타나면 정보를 검토하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-158">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="c3919-159">다음 페이지에서 **스토어에서 선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-159">On the next page, click **Choose from the Store**.</span></span>

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c3919-161">나타나는 **추가 기능** 선택 페이지에서 검색 상자를 **클릭하고** 보고서 **메시지** 를 입력한 다음 검색 검색 아이콘 **을** ![ ](../../media/search-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-161">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c3919-162">결과 목록에서 보고서 **메시지를 찾은 다음** 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-162">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![추가 기능 검색 결과 선택](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="c3919-164">나타나는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-164">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="c3919-165">나타나는 **추가 기능 구성** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-165">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c3919-166">**할당된 사용자:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-166">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c3919-167">**모든** 사용자(기본값)</span><span class="sxs-lookup"><span data-stu-id="c3919-167">**Everyone** (default)</span></span>
     - <span data-ttu-id="c3919-168">**특정 사용자/그룹**</span><span class="sxs-lookup"><span data-stu-id="c3919-168">**Specific users / groups**</span></span>
     - <span data-ttu-id="c3919-169">**저뿐이에요**</span><span class="sxs-lookup"><span data-stu-id="c3919-169">**Just me**</span></span>

   - <span data-ttu-id="c3919-170">**배포 방법:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-170">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c3919-171">**고정(기본값)**: 추가 기능은 지정된 사용자에게 자동으로 배포되며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-171">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c3919-172">**사용** 가능: 사용자는 홈 추가  기능 추가 기능 관리자가 관리하는 에서 추가 기능을 설치할 \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-172">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c3919-173">**선택** 사항: 추가 기능을 지정된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-173">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![추가 기능 페이지 구성](../../media/configure-add-in.png)

   <span data-ttu-id="c3919-175">완료되면 배포를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-175">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="c3919-176">보고서 **메시지** 배포 페이지에 나타나는 진행률 보고서와 추가 기능 배포 확인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-176">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c3919-177">정보를 읽은 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-177">After you read the information, click **Next**.</span></span>

   ![보고서 메시지 배포 페이지](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="c3919-179">추가 기능 발표 **페이지가** 나타나면 정보를 검토하고 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-179">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![추가 기능 페이지 발표](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="c3919-181">보고서 메시지 추가 기능의 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="c3919-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="c3919-182">Microsoft 365 관리 센터에서 의 설정 추가 기능  페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="c3919-183">추가 기능 페이지가  없는 경우 통합 앱 **페이지 설정** 통합 앱 추가 기능 링크로 \>  \>  이동합니다. </span><span class="sxs-lookup"><span data-stu-id="c3919-183">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![새 Add-Ins 관리 센터의 서비스 및 Microsoft 365 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="c3919-185">보고서 메시지 **추가** 기능을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-185">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="c3919-186">보고서 **메시지 편집** 플라이아웃이 나타나면 조직에 적합한 설정을 검토하고 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-186">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c3919-187">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-187">When you're finished, click **Save**.</span></span>

   ![설정 메시지 추가 기능의 추가 기능 확인](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="c3919-189">피싱 보고서 추가 기능 얻기</span><span class="sxs-lookup"><span data-stu-id="c3919-189">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="c3919-190">직접 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="c3919-190">Get the add-in for yourself</span></span>

1. <span data-ttu-id="c3919-191">에서 Microsoft AppSource로 이동하여 피싱 보고 추가 <https://appsource.microsoft.com/marketplace/apps> 기능을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-191">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="c3919-192">지금 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-192">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="c3919-193">나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-193">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c3919-194">직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-194">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c3919-195">추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-195">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c3919-196">이 Outlook 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-196">In Outlook, the icon looks like this:</span></span>

  ![보고서 피싱 추가 기능 아이콘에 대한 Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c3919-198">웹 Outlook 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-198">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="c3919-199">![Outlook 피싱 추가 기능 아이콘에 표시](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="c3919-199">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="c3919-200">조직에 대한 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="c3919-200">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c3919-201">추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-201">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c3919-202">Microsoft 365 관리 센터에서 의 설정 추가 기능  페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-202">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="c3919-203">추가 기능 페이지가  없는 경우 통합 앱 **페이지 설정** 통합 앱 추가 기능 링크로 \>  \>  이동합니다. </span><span class="sxs-lookup"><span data-stu-id="c3919-203">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c3919-204">페이지 **맨** 위에 있는 추가 기능 배포를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-204">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="c3919-206">새 **추가 기능** 배포 플라이아웃이 나타나면 정보를 검토하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-206">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="c3919-207">다음 페이지에서 **스토어에서 선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-207">On the next page, click **Choose from the Store**.</span></span>

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c3919-209">나타나는 **추가 기능** 선택 페이지에서 검색 상자를 **클릭하고** 피싱 **보고를** 입력한 다음 검색 **검색** 아이콘 을 ![ ](../../media/search-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-209">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c3919-210">결과 목록에서 피싱 **보고를 찾은** 다음 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-210">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="c3919-211">나타나는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-211">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="c3919-212">나타나는 **추가 기능 구성** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-212">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c3919-213">**할당된 사용자:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-213">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c3919-214">**모든** 사용자(기본값)</span><span class="sxs-lookup"><span data-stu-id="c3919-214">**Everyone** (default)</span></span>
     - <span data-ttu-id="c3919-215">**특정 사용자/그룹**</span><span class="sxs-lookup"><span data-stu-id="c3919-215">**Specific users / groups**</span></span>
     - <span data-ttu-id="c3919-216">**저뿐이에요**</span><span class="sxs-lookup"><span data-stu-id="c3919-216">**Just me**</span></span>

   - <span data-ttu-id="c3919-217">**배포 방법:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-217">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c3919-218">**고정(기본값)**: 추가 기능은 지정된 사용자에게 자동으로 배포되며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-218">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c3919-219">**사용** 가능: 사용자는 홈 추가  기능 추가 기능 관리자가 관리하는 에서 추가 기능을 설치할 \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-219">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c3919-220">**선택** 사항: 추가 기능을 지정된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-220">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="c3919-221">완료되면 배포를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-221">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="c3919-222">보고서 **피싱** 배포 페이지에 나타나는 진행률 보고서와 추가 기능 배포 확인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-222">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c3919-223">정보를 읽은 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-223">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="c3919-224">추가 기능 발표 **페이지가** 나타나면 정보를 검토하고 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3919-224">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="c3919-225">피싱 보고 추가 기능 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="c3919-225">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="c3919-226">Microsoft 365 관리 센터에서 의 설정 추가 기능  페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-226">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="c3919-227">추가 기능 페이지가  없는 경우 통합 앱 **페이지 설정** 통합 앱 추가 기능 링크로 \>  \>  이동합니다. </span><span class="sxs-lookup"><span data-stu-id="c3919-227">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c3919-228">피싱 **보고 추가** 기능을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-228">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="c3919-229">조직에 **적합한** 설정이 나타나는 피싱 보고서 편집 플라이아웃에서 설정을 검토하고 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c3919-230">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c3919-230">When you're finished, click **Save**.</span></span>
