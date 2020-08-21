---
title: 보고서 메시지 추가 기능을 사용하도록 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: 개별 사용자 또는 전체 조직에 대해 Outlook 및 웹용 Outlook용 보고서 메시지 추가 기능을 사용하도록 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 45f67e4c88d311254a0d922baed66178c3f672a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826640"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="f0d60-103">보고서 메시지 추가 기능을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f0d60-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="f0d60-104">Exchange Online 사서함을 사용 하 고 Microsoft 365 조직의 관리자는 보안 도메인 준수 센터에서 제출 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f0d60-105">자세한 내용은 [관리자 제출 사용을 참조하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f0d60-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f0d60-106">Outlook 및 웹용 Outlook(이전의 Outlook Web App)에 대한 보고서 메시지 추가 기능을 사용하면 사용자들이 가양성(잘못된 전자 메일로 표시) 또는 거짓 부정(잘못된 전자 메일이 허용된 경우)을 분석용으로 쉽게 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="f0d60-107">Microsoft는 이러한 제출을 사용하여 전자 메일 보호 기술의 효율성을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="f0d60-108">예를 들어 다른 사용자가 피싱으로 많은 메시지를 보고한다고 가정해 보시기 바라고 가정해보시다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="f0d60-109">보안 대시보드 및 기타 [보고서의 이 정보가](security-dashboard.md) 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="f0d60-110">조직의 보안 팀은 이 정보를 피싱 방지 정책을 업데이트해야 할 수 있다는 명시로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="f0d60-111">또는 사용자가 보고서 메시지 추가 기능을 사용하여 정크 메일이 정크 메일로 플래그가 지정된 대량의 메시지를 보고하는 경우 조직의 보안 팀에서 스팸 방지 [정책을 조정해야 할 수도 있습니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f0d60-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="f0d60-112">또한 조직에서 [Office 365 Advanced Threat Protection Plan 1 또는](office-365-atp.md) [Plan 2를](office-365-ti.md)사용하는 경우 보고서 메시지 추가 기능은 보안 정책을 검토하고 업데이트하는 데 사용할 수 있는 유용한 정보를 조직의 보안 팀에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="f0d60-113">관리자는 조직의 보고서 메시지 추가 기능을 사용하도록 설정할 수 있고 개별 사용자가 자신을 위해 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="f0d60-114">개별 사용자이면 보고서 메시지 추가 [기능을 자신을 위해 사용하도록 설정할 수 있습니다.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="f0d60-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="f0d60-115">전역 관리자이거나 Exchange Online 관리자이고 Exchange가 OAuth 인증을 사용하도록 구성된 경우 조직에 대해 [보고서 메시지 추가 기능을 사용하도록 설정할 수 있습니다.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="f0d60-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="f0d60-116">이제 보고서 메시지 추가 기능을 중앙 집중식 [배포를 통해 사용할 수 있습니다.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="f0d60-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0d60-117">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f0d60-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f0d60-118">보고서 메시지 추가 기능은 대부분의 Microsoft 365 구독 및 다음 제품에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="f0d60-119">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="f0d60-119">Outlook on the web</span></span>
  - <span data-ttu-id="f0d60-120">Outlook 2013 SP1 이상</span><span class="sxs-lookup"><span data-stu-id="f0d60-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="f0d60-121">Mac용 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0d60-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="f0d60-122">엔터프라이즈용 Microsoft 365 앱에 포함된 Outlook</span><span class="sxs-lookup"><span data-stu-id="f0d60-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="f0d60-123">보고서 메시지 추가 기능은 온-프레미스 Exchange 조직의 사서함에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="f0d60-124">지정한 사서함으로 복사 또는 리디렉션하도록 보고된 메시지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f0d60-125">자세한 내용은 [Exchange Online에서 스팸 및 피싱 메시지의 사용자 전송을 위한 사서함 지정을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f0d60-125">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="f0d60-126">보고서 메시지 추가 기능을 사용하려면 기존 웹 브라우저가 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="f0d60-127">그러나 추가 기능을 사용할 수 없거나 예상대로 작동하지 않는 경우 다른 브라우저를 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="f0d60-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="f0d60-128">조직 설치의 경우에는 조직에서 OAuth 인증을 사용하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="f0d60-129">자세한 내용은 [요약에서 추가 기능의 중앙 집중식 배포가 조직에서 작동하는지 확인하세요.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="f0d60-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="f0d60-130">관리자는 Global admins 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="f0d60-131">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0d60-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="f0d60-132">자신을 위한 보고서 메시지 추가 기능 가져오기</span><span class="sxs-lookup"><span data-stu-id="f0d60-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="f0d60-133">Microsoft AppSource로 이동한 <https://appsource.microsoft.com/marketplace/apps> 후 보고서 메시지 추가 기능을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="f0d60-134">보고서 메시지 추가 기능으로 직접 이동하려면 다음으로 <https://appsource.microsoft.com/product/office/wa104381180> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="f0d60-135">지금 **액세스를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-135">Click **GET IT NOW**.</span></span>

   ![보고 메시지 - 가져오기](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="f0d60-137">표시되는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 후 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="f0d60-138">회사 또는 학교 계정(비즈니스 용도) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="f0d60-139">추가 기능이 설치되어 사용하도록 설정되면 다음 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="f0d60-140">Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-140">In Outlook, the icon looks like this:</span></span>

  ![Outlook용 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="f0d60-142">웹용 Outlook에서 아이콘은 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-142">In Outlook on the web, the icon looks like this:</span></span>

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="f0d60-144">추가 기능을 사용하는 방법에 대한 자세한 내용은 보고서 [메시지 추가 기능 사용을 참조하세요.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="f0d60-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="f0d60-145">조직용 보고서 메시지 추가 기능 받기 및 사용</span><span class="sxs-lookup"><span data-stu-id="f0d60-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="f0d60-146">추가 기능이 조직에 나타나려면 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="f0d60-147">Microsoft 365 관리 센터에서 추가 **기능 & 페이지로** 이동한 다음 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 추가 기능 **배포를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-147">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="f0d60-149">표시되는 새 **추가 기능 배포 플라이아웃에서** 정보를 검토한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="f0d60-150">다음 페이지에서 Choose from the **Store(스토어에서 선택)을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-150">On the next page, click **Choose from the Store**.</span></span>

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="f0d60-152">**나타나는 추가 기능** 선택 페이지에서 보고서 메시지를 **입력하고**검색 아이콘을 **Search** **Search** ![ ](../../media/search-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="f0d60-153">결과 목록에서 보고서 메시지를 찾은 **다음 추가를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![추가 기능 검색 결과 선택](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="f0d60-155">표시되는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 후 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="f0d60-156">추가 **기능 구성 페이지가** 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f0d60-157">**할당된**사용자: 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="f0d60-158">**모든** 사용자(기본값)</span><span class="sxs-lookup"><span data-stu-id="f0d60-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="f0d60-159">**특정 사용자/그룹**</span><span class="sxs-lookup"><span data-stu-id="f0d60-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="f0d60-160">**저뿐이에요**</span><span class="sxs-lookup"><span data-stu-id="f0d60-160">**Just me**</span></span>

   - <span data-ttu-id="f0d60-161">**배포 방법:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="f0d60-162">**고정됨(기본값):** 추가 기능이 지정된 사용자에게 자동으로 배포되며 사용자가 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="f0d60-163">**사용**가능: 사용자가 홈 가져오기 추가 **기능에서** \> **관리자 관리를 통해 추가 기능을** \> **설치할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="f0d60-164">**선택**사항 : 추가 기능이 지정된 사용자에게 자동으로 배포되지만 이를 제거하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![추가 기능 페이지 구성](../../media/configure-add-in.png)

   <span data-ttu-id="f0d60-166">작업을 마치면 배포를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="f0d60-167">보고서 **보고서 배포 페이지에** 표시되는 보고서, 추가 기능이 배포되었다는 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="f0d60-168">정보를 확인한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-168">After you read the information, click **Next**.</span></span>

   ![보고서 메시지 배포 페이지](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="f0d60-170">On the **Announce add-in** page that appears, and then click **Close.**</span><span class="sxs-lookup"><span data-stu-id="f0d60-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![추가 기능 페이지 알림](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="f0d60-172">보고서 메시지 추가 기능을 사용하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="f0d60-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="f0d60-173">추가 기능이 할당된 사람은 다음 아이콘을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="f0d60-174">Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-174">In Outlook, the icon looks like this:</span></span>

  ![Outlook용 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="f0d60-176">웹용 Outlook에서 아이콘은 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-176">In Outlook on the web, the icon looks like this:</span></span>

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="f0d60-178">보고서 메시지 추가 기능에 대해 사용자에게 이를 보낼 때는 보고서 메시지 추가 [기능을 사용하기 위한 링크를 포함합니다.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="f0d60-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="f0d60-179">보고서 메시지 추가 기능에 대한 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="f0d60-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="f0d60-180">Microsoft 365 관리 센터에서 서비스 대시보드 **& 페이지로** <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![새 Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="f0d60-182">보고서 메시지 추가 **기능을 찾아** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="f0d60-183">표시되는 보고서 **메시지 플라이아웃에서** 해당 조직에 맞게 설정을 검토 및 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="f0d60-184">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-184">When you're finished, click **Save**.</span></span>

   ![보고서 메시지 추가 기능 설정](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="f0d60-186">보고된 메시지 보기 및 검토</span><span class="sxs-lookup"><span data-stu-id="f0d60-186">View and review reported messages</span></span>

<span data-ttu-id="f0d60-187">사용자가 Microsoft에 보고한 메시지를 검토하려면 다음 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="f0d60-188">관리자 제출 포털을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="f0d60-189">자세한 내용은 [Microsoft에 대한 사용자 제출 보기를 참조하세요.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f0d60-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="f0d60-190">보고된 메시지의 복사본을 보낼 메일 흐름 규칙(전송 규칙이라고도 함)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0d60-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="f0d60-191">자세한 내용은 메일 흐름 [규칙을 사용하여 사용자가 Microsoft에 보고한 내용을 확인합니다.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f0d60-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
