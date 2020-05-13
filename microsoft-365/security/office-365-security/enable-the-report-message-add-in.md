---
title: 보고서 메시지 추가 기능을 사용하도록 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 개별 사용자 또는 전체 조직에 대해 Outlook 및 웹용 outlook 용 보고서 메시지 추가 기능을 사용 하도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 67fe2112e5d507ac1f0dc78ffa3534ebc9874916
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209490"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="d843b-103">보고서 메시지 추가 기능을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d843b-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="d843b-104">Exchange Online 사서함이 있는 Microsoft 365 조직의 관리자 인 경우 보안 & 준수 센터에서 전송 포털을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="d843b-105">자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d843b-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="d843b-106">Outlook 및 웹용 Outlook에 대 한 보고서 메시지 추가 기능 (이전의 Outlook Web App)은 사용자가 가양성 (잘못 된 것으로 표시 된 전자 메일) 또는 거짓 네거티브 (잘못 된 전자 메일 허용)를 Microsoft와 해당 계열사로 쉽게 보고할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="d843b-107">Microsoft는 이러한 전송을 사용 하 여 전자 메일 보호 기술의 효율성을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="d843b-108">예를 들어 사용자가 많은 양의 메시지를 피싱 메일로 보고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="d843b-109">이 정보는 [보안 대시보드](security-dashboard.md) 및 기타 보고서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="d843b-110">조직의 보안 팀에서이 정보를 사용 하 여 피싱 방지 정책을 업데이트 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="d843b-111">또는 사용자가 보고서 메시지 추가 기능을 사용 하 여 정크 메일로 플래그를 지정 하지 않은 많은 메시지를 보고 하는 경우 조직의 보안 팀이 [스팸 방지 정책을](configure-your-spam-filter-policies.md)조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d843b-112">또한 조직에서 [Office 365 Advanced Threat Protection 계획 1](office-365-atp.md) 또는 [계획 2](office-365-ti.md)를 사용 하는 경우 보고서 메시지 추가 기능은 조직의 보안 팀에 게 보안 정책을 검토 하 고 업데이트 하는 데 사용할 수 있는 유용한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="d843b-113">관리자는 조직에 대 한 보고서 메시지 추가 기능을 사용 하도록 설정 하 고 개별 사용자는 자신을 위해 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="d843b-114">개별 사용자 [의 경우에는 보고서 메시지 추가 기능을 사용 하도록 설정할](#get-the-report-message-add-in-for-yourself)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="d843b-115">전역 관리자 또는 Exchange Online 관리자이 고 Exchange가 OAuth 인증을 사용 하도록 구성 된 경우 [조직에 대 한 보고서 메시지 추가 기능을 사용 하도록 설정할](#get-and-enable-the-report-message-add-in-for-your-organization)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="d843b-116">이제 [중앙 집중식 배포](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)를 통해 보고서 메시지 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d843b-117">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d843b-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d843b-118">보고서 메시지 추가 기능 이란 대부분의 Microsoft 365 구독과 다음 제품에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="d843b-119">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="d843b-119">Outlook on the web</span></span>
  - <span data-ttu-id="d843b-120">Outlook 2013 SP1 이상</span><span class="sxs-lookup"><span data-stu-id="d843b-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="d843b-121">Mac용 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d843b-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="d843b-122">Microsoft 365 for Enterprise 앱에 포함 된 Outlook</span><span class="sxs-lookup"><span data-stu-id="d843b-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="d843b-123">보고서 메시지 추가 기능은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="d843b-124">온-프레미스 Exchange 조직의 사서함</span><span class="sxs-lookup"><span data-stu-id="d843b-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="d843b-125">GCC, GCC HIGH 또는 DoD 구독</span><span class="sxs-lookup"><span data-stu-id="d843b-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="d843b-126">보고 된 메시지가 사용자가 지정한 사서함으로 복사 되거나 리디렉션되도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="d843b-127">자세한 내용은 [Exchange Online의 스팸 및 피싱 메시지에 대 한 사용자 제출을 위한 사서함 지정](user-submission.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d843b-127">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="d843b-128">기존 웹 브라우저가 보고서 메시지 추가 기능을 사용 하 여 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-128">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="d843b-129">그러나 추가 기능이 사용 가능 하지 않거나 예상 대로 작동 하지 않는 경우 다른 브라우저를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d843b-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="d843b-130">조직 설치의 경우 OAuth 인증을 사용 하도록 조직을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="d843b-131">자세한 내용은 [조직에 대 한 추가 기능의 중앙 집중식 배포가 작동 하는지 확인](../../admin/manage/centralized-deployment-of-add-ins.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d843b-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="d843b-132">관리자는 전역 관리자 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="d843b-133">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d843b-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="d843b-134">사용자를 위한 보고서 메시지 추가 기능 가져오기</span><span class="sxs-lookup"><span data-stu-id="d843b-134">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="d843b-135">Microsoft AppSource로 이동 하 여 <https://appsource.microsoft.com/marketplace/apps> 보고서 메시지 추가 기능을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="d843b-136">보고서 메시지 추가 기능으로 바로 이동 하려면로 이동 <https://appsource.microsoft.com/product/office/wa104381180> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-136">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="d843b-137">**지금 다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-137">Click **GET IT NOW**.</span></span>

   ![메시지 보고-지금 받기](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="d843b-139">대화 상자가 나타나면 사용 약관 및 개인 정보 취급 방침을 검토 하 고 **계속**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-139">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="d843b-140">회사 또는 학교 계정 (비즈니스용으로 사용) 또는 Microsoft 계정 (개인적으로 사용)을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-140">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="d843b-141">추가 기능을 설치 하 고 사용 하도록 설정한 후에는 다음 아이콘이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-141">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="d843b-142">Outlook에서 아이콘은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-142">In Outlook, the icon looks like this:</span></span>

  ![Outlook에 대 한 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="d843b-144">웹용 Outlook에서 아이콘은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-144">In Outlook on the web, the icon looks like this:</span></span>

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="d843b-146">이 추가 기능을 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능 사용](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d843b-146">To learn how to use the add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="d843b-147">조직에 대 한 보고서 메시지 추가 기능 가져오기 및 사용</span><span class="sxs-lookup"><span data-stu-id="d843b-147">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="d843b-148">조직에 추가 기능을 표시 하는 데 최대 12 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-148">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="d843b-149">Microsoft 365 관리 센터에서 **서비스 & 추가** 기능 페이지로 이동한 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 후 **추가 기능 배포**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-149">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="d843b-151">나타나는 **새 추가 기능** 플라이 아웃을 배포 합니다 .에서 정보를 검토 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="d843b-152">다음 페이지에서 **스토어에서 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-152">On the next page, click **Choose from the Store**.</span></span>

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="d843b-154">표시 되는 **추가 기능 선택** 페이지에서 **검색** 상자를 클릭 하 고 **보고서 메시지**를 입력 한 다음 **검색** ![ 검색 아이콘을 클릭 ](../../media/search-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="d843b-155">결과 목록에서 **보고서 메시지** 를 찾은 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![추가 기능 검색 결과 선택](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="d843b-157">대화 상자가 나타나면 라이선스 및 개인 정보 보호 정보를 검토 하 고 **계속**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="d843b-158">**추가 기능 구성** 페이지가 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d843b-159">**할당 된 사용자**: 다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="d843b-160">**모든 사람** (기본값)</span><span class="sxs-lookup"><span data-stu-id="d843b-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="d843b-161">**특정 사용자/그룹**</span><span class="sxs-lookup"><span data-stu-id="d843b-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="d843b-162">**저뿐이에요**</span><span class="sxs-lookup"><span data-stu-id="d843b-162">**Just me**</span></span>

   - <span data-ttu-id="d843b-163">**배포 방법**: 다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="d843b-164">**Fixed (기본값)**: 추가 기능이 지정 된 사용자에 게 자동으로 배포 되며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="d843b-165">**사용 가능**: 사용자가 **홈** 에 추가 기능을 설치할 수 있습니다 \> **Get add-ins** \> **관리 관리**를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="d843b-166">**선택 사항**: 추가 기능은 지정 된 사용자에 게 자동으로 배포 되지만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![추가 기능 페이지 구성](../../media/configure-add-in.png)

   <span data-ttu-id="d843b-168">작업이 완료 되 면 **배포**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-168">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="d843b-169">표시 되는 **보고서 메시지 배포** 페이지에 진행률 보고서와 추가 기능이 배포 되었다는 확인이 차례로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="d843b-170">정보를 읽은 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-170">After you read the information, click **Next**.</span></span>

   ![보고서 메시지 배포 페이지](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="d843b-172">표시 되는 **추가 기능** 페이지에서 정보를 검토 하 고 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![추가 기능 페이지 알림](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="d843b-174">보고서 메시지 추가 기능을 사용 하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="d843b-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="d843b-175">추가 기능이 할당 된 사용자는 다음 아이콘을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="d843b-176">Outlook에서 아이콘은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-176">In Outlook, the icon looks like this:</span></span>

  ![Outlook에 대 한 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="d843b-178">웹용 Outlook에서 아이콘은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-178">In Outlook on the web, the icon looks like this:</span></span>

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="d843b-180">사용자에 게 보고서 메시지 추가 기능에 대 한 알림을 보내는 경우 [보고서 메시지 추가 기능을 사용](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)하는 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="d843b-181">보고서 메시지 추가 기능의 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="d843b-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="d843b-182">Microsoft 365 관리 센터에서 **서비스 & 추가 기능** 페이지로 이동 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-182">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![새 Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="d843b-184">**보고서 메시지** 추가 기능을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="d843b-185">표시 된 **보고서 메시지** 플라이 아웃 편집에서 조직에 적합 한 설정을 검토 하 고 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="d843b-186">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-186">When you're finished, click **Save**.</span></span>

   ![보고서 메시지 추가 기능에 대 한 설정](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="d843b-188">보고 된 메시지 보기 및 검토</span><span class="sxs-lookup"><span data-stu-id="d843b-188">View and review reported messages</span></span>

<span data-ttu-id="d843b-189">사용자가 Microsoft에 보고 하는 메시지를 검토 하려면 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-189">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="d843b-190">관리자 전송 포털을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-190">Use the Admin Submissions portal.</span></span> <span data-ttu-id="d843b-191">자세한 내용은 [Microsoft에 대 한 사용자 제출 보기](admin-submission.md#view-user-submissions-to-microsoft)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d843b-191">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="d843b-192">메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들어 보고 된 메시지의 복사본을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d843b-192">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="d843b-193">자세한 내용은 [메일 흐름 규칙을 사용 하 여 사용자가 Microsoft에 보고 하는 항목 보기](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d843b-193">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
