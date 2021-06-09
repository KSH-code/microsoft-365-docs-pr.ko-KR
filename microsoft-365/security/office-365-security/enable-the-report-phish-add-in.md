---
title: 피싱 보고서 추가 기능 사용
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 웹, 개별 사용자 또는 전체 조직에 대해 Outlook 및 Outlook 피싱 보고서 추가 기능을 사용하도록 설정하는 방법을 학습합니다.
ms.openlocfilehash: 44fa55a82462de336982d3af2e3996c14699fd7c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625392"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="d80fd-103">보고서 피싱 추가 기능을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d80fd-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="d80fd-104">사서함이 있는 Microsoft 365 조직의 관리자인 Exchange Online 보안 및 준수 센터의 제출 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="d80fd-105">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d80fd-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="d80fd-106">웹에서 Outlook 및 Outlook(이전의 Outlook Web App)에 대한 피싱 보고 추가 기능을 사용하면 사용자가 분석을 위해 Microsoft 및 계열사에 가음성(나쁜 것으로 표시된 좋은 전자 메일) 또는 거짓 부정(잘못된 전자 메일 허용)을 쉽게 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="d80fd-107">Microsoft는 이러한 제출을 사용하여 전자 메일 보호 기술의 효율성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="d80fd-108">예를 들어 피싱 보고 추가 기능을 사용하여 많은 메시지를 보고하는 사람이 많은 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="d80fd-109">이 정보는 보안 대시보드 [및](security-dashboard.md) 기타 보고서에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="d80fd-110">조직의 보안 팀은 이 정보를 피싱 방지 정책을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="d80fd-111">보고서 메시지 또는 피싱 보고 추가 기능을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="d80fd-112">사용자가 스팸 및 피싱 메시지를 모두 보고하게 하려는 경우 조직에 보고서 메시지 추가 기능을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="d80fd-113">자세한 내용은 보고서 메시지 추가 기능 [사용 을 참조하세요.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="d80fd-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="d80fd-114">피싱 보고 추가 기능은 피싱 메시지만 보고하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="d80fd-115">관리자는 조직에 대해 피싱 보고 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="d80fd-116">개별 사용자인 경우 피싱 보고 추가 기능을 직접 사용하도록 설정할 [수 있습니다.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="d80fd-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="d80fd-117">전역 관리자 또는 Exchange Online 관리자로서 Exchange OAuth 인증을 사용하도록 구성된 경우 조직에 대해 피싱 보고 추가 기능을 사용하도록 설정할 [수 있습니다.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="d80fd-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="d80fd-118">이제 보고서 피싱 Add-In 중앙 집중식 [배포를 통해 사용할 수 있습니다.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="d80fd-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d80fd-119">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d80fd-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d80fd-120">피싱 보고서 추가 기능에서는 대부분의 Microsoft 365 및 다음 제품과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="d80fd-121">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="d80fd-121">Outlook on the web</span></span>
  - <span data-ttu-id="d80fd-122">Outlook 2013 SP1 이상</span><span class="sxs-lookup"><span data-stu-id="d80fd-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="d80fd-123">Mac용 Outlook 2016 이상</span><span class="sxs-lookup"><span data-stu-id="d80fd-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="d80fd-124">Outlook 앱용 Microsoft 365 포함된 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d80fd-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="d80fd-125">Outlook iOS 및 Android용 앱</span><span class="sxs-lookup"><span data-stu-id="d80fd-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="d80fd-126">피싱 보고서 추가 기능을 조직에 있는 공유 사서함이나 조직에 있는 사서함에 사용할 Exchange 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="d80fd-127">보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="d80fd-128">자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d80fd-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="d80fd-129">기존 웹 브라우저는 피싱 보고 추가 기능에서 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="d80fd-130">그러나 추가 기능을 사용할 수 없는 경우 또는 예상대로 작동하지 않는 경우 다른 브라우저를 사용해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="d80fd-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="d80fd-131">조직 설치의 경우 OAuth 인증을 사용하도록 조직을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="d80fd-132">자세한 내용은 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조하세요.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="d80fd-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="d80fd-133">관리자는 전역 관리자 역할 그룹의 구성원이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="d80fd-134">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d80fd-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="d80fd-135">직접 피싱 보고 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="d80fd-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="d80fd-136">에서 Microsoft AppSource로 이동하여 피싱 보고 추가 <https://appsource.microsoft.com/marketplace/apps> 기능을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="d80fd-137">지금 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="d80fd-138">나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="d80fd-139">직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="d80fd-140">추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="d80fd-141">이 Outlook 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-141">In Outlook, the icon looks like this:</span></span>

  ![보고서 피싱 추가 기능 아이콘에 대한 Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="d80fd-143">웹 Outlook 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 피싱 추가 기능 아이콘에 표시](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="d80fd-145">조직에 대해 피싱 보고 추가 기능 확인 및 사용</span><span class="sxs-lookup"><span data-stu-id="d80fd-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="d80fd-146">추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="d80fd-147">Microsoft 365 관리 센터에서 의 설정 추가 기능  페이지로 이동합니다. 추가 기능 페이지가 없는 경우 통합 앱 페이지 맨 위에 있는 설정 통합 앱 추가 기능 링크로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="d80fd-148">페이지 **맨** 위에 있는 추가 기능 배포를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="d80fd-150">새 **추가 기능** 배포 플라이아웃이 나타나면 정보를 검토하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="d80fd-151">다음 페이지에서 **스토어에서 선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-151">On the next page, click **Choose from the Store**.</span></span>

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="d80fd-153">나타나는 **추가 기능** 선택 페이지에서 검색 상자를 **클릭하고** 피싱 **보고를** 입력한 다음 검색 **검색** 아이콘 을 ![ ](../../media/search-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="d80fd-154">결과 목록에서 피싱 **보고를 찾은** 다음 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="d80fd-155">나타나는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 다음 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="d80fd-156">나타나는 **추가 기능 구성** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d80fd-157">**할당된 사용자:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="d80fd-158">**모든** 사용자(기본값)</span><span class="sxs-lookup"><span data-stu-id="d80fd-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="d80fd-159">**특정 사용자/그룹**</span><span class="sxs-lookup"><span data-stu-id="d80fd-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="d80fd-160">**저뿐이에요**</span><span class="sxs-lookup"><span data-stu-id="d80fd-160">**Just me**</span></span>

   - <span data-ttu-id="d80fd-161">**배포 방법:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="d80fd-162">**고정(기본값)**: 추가 기능은 지정된 사용자에게 자동으로 배포되며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="d80fd-163">**사용** 가능: 사용자는 홈 추가  기능 추가 기능 관리자가 관리하는 에서 추가 기능을 설치할 \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="d80fd-164">**선택** 사항: 추가 기능을 지정된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="d80fd-165">완료되면 배포를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="d80fd-166">보고서 **피싱** 배포 페이지에 나타나는 진행률 보고서와 추가 기능 배포 확인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="d80fd-167">정보를 읽은 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="d80fd-168">추가 기능 발표 **페이지가** 나타나면 정보를 검토하고 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="d80fd-169">피싱 보고서 추가 기능을 사용하는 방법 학습</span><span class="sxs-lookup"><span data-stu-id="d80fd-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="d80fd-170">추가 기능을 할당한 사용자에게는 다음 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="d80fd-171">이 Outlook 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-171">In Outlook, the icon looks like this:</span></span>

  ![보고서 피싱 추가 기능 아이콘에 대한 Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="d80fd-173">웹 Outlook 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 피싱 추가 기능 아이콘에 표시됩니다.](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="d80fd-175">피싱 보고 추가 기능 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="d80fd-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="d80fd-176">Microsoft 365 관리 센터에서 의 설정 추가 기능  페이지로 이동합니다. 추가 기능 페이지가 없는 경우 통합 앱 페이지 맨 위에 있는 설정 통합 앱 추가 기능 링크로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d80fd-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="d80fd-177">피싱 **보고 추가** 기능을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="d80fd-178">조직에 **적합한** 설정이 나타나는 피싱 보고서 편집 플라이아웃에서 설정을 검토하고 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="d80fd-179">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="d80fd-180">보고된 메시지 보기 및 검토</span><span class="sxs-lookup"><span data-stu-id="d80fd-180">View and review reported messages</span></span>

<span data-ttu-id="d80fd-181">사용자가 Microsoft에 보고하는 메시지를 검토할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="d80fd-182">관리 제출 포털을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d80fd-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="d80fd-183">자세한 내용은 [Microsoft에 대한 사용자 제출 보기를 참조하세요.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="d80fd-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="d80fd-184">메일 흐름 규칙(전송 규칙)을 만들어 보고된 메시지의 복사본을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d80fd-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="d80fd-185">자세한 내용은 메일 흐름 규칙을 사용하여 Microsoft에 보고하는 사용자 [확인을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="d80fd-185">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
