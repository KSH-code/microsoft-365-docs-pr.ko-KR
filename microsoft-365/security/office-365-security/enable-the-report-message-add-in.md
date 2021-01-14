---
title: 보고서 메시지 추가 기능을 사용하도록 설정
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: 개별 사용자 또는 전체 조직에 대해 Outlook 및 웹용 Outlook에 대해 보고서 메시지 추가 기능을 사용하도록 설정하는 방법을 자세히 알아보습니다.
ms.openlocfilehash: 13721317c33cf207f27cd8b98fb6d32864651847
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864999"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="a2b88-103">보고서 메시지 추가 기능을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="a2b88-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="a2b88-104">Exchange Online 사서함이 있는 Microsoft 365 조직의 관리자인 경우 보안 및 준수 센터에서 제출 포털을 & 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a2b88-105">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 [Microsoft에 제출하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a2b88-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="a2b88-106">Outlook 및 웹용 Outlook(이전의 Outlook Web App)에 대한 피싱 보고 추가 기능을 사용하면 사용자가 분석을 위해 Microsoft 및 계열사에 가음성(양호한 전자 메일이 허용된 양호한 전자 메일)을 쉽게 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="a2b88-107">Microsoft는 이러한 제출을 사용하여 전자 메일 보호 기술의 효율성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="a2b88-108">예를 들어 사용자가 보고서 메시지 추가 기능을 사용하여 정크 메일 아님으로 플래그가 지정된 많은 메시지를 보고하는 경우 조직의 보안 팀에서 스팸 방지 정책을 조정해야 할 수 [있습니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a2b88-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a2b88-109">보고서 메시지 또는 피싱 보고 추가 기능을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="a2b88-110">사용자가 피싱 메시지만 보고하게 하려는 경우 조직에 피싱 보고서 추가 기능을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="a2b88-111">자세한 내용은 보고서 피싱 추가 기능 [사용을 참조하세요.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="a2b88-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="a2b88-112">보고서 메시지 추가 기능은 스팸 메시지와 피싱 메시지를 모두 보고하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="a2b88-113">관리자는 조직에 대해 보고서 메시지 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="a2b88-114">개별 사용자인 경우 보고서 메시지 추가 기능을 직접 사용하도록 설정할 [수 있습니다.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="a2b88-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="a2b88-115">전역 관리자 또는 Exchange Online 관리자인 경우 Exchange가 OAuth 인증을 사용하도록 구성된 경우 조직에 대해 보고서 메시지 추가 기능을 사용하도록 설정할 [수 있습니다.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="a2b88-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="a2b88-116">보고서 메시지 Add-In 중앙 집중식 배포를 통해 사용할 [수 있습니다.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="a2b88-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a2b88-117">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="a2b88-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a2b88-118">보고서 메시지 추가 기능에서는 대부분의 Microsoft 365 구독 및 다음 제품과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="a2b88-119">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="a2b88-119">Outlook on the web</span></span>
  - <span data-ttu-id="a2b88-120">Outlook 2013 SP1 이상</span><span class="sxs-lookup"><span data-stu-id="a2b88-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="a2b88-121">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="a2b88-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="a2b88-122">엔터프라이즈용 Microsoft 365 앱에 포함된 Outlook</span><span class="sxs-lookup"><span data-stu-id="a2b88-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="a2b88-123">보고서 메시지 추가 기능을 Exchange 조직의 사서함에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="a2b88-124">보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="a2b88-125">자세한 내용은 사용자 제출 [정책을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a2b88-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="a2b88-126">기존 웹 브라우저는 보고서 메시지 추가 기능에서 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="a2b88-127">그러나 추가 기능을 사용할 수 없는 경우 또는 예상대로 작동하지 않는 경우 다른 브라우저를 시도해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="a2b88-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="a2b88-128">조직 설치의 경우 OAuth 인증을 사용하도록 조직을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="a2b88-129">자세한 내용은 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조하세요.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="a2b88-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="a2b88-130">관리자는 전역 관리자 역할 그룹의 구성원이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="a2b88-131">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2b88-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="a2b88-132">직접 보고서 메시지 추가 기능 확인</span><span class="sxs-lookup"><span data-stu-id="a2b88-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="a2b88-133">Microsoft AppSource로 이동하여 보고서 메시지 추가 기능을 <https://appsource.microsoft.com/marketplace/apps> 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="a2b88-134">보고서 메시지 추가 기능으로 직접 이동한 다음 <https://appsource.microsoft.com/product/office/wa104381180> 으로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2b88-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="a2b88-135">지금 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-135">Click **GET IT NOW**.</span></span>

   ![보고서 메시지 - 지금 확인](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="a2b88-137">나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토하고 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="a2b88-138">직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="a2b88-139">추가 기능을 설치하고 사용하도록 설정하면 다음 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="a2b88-140">Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-140">In Outlook, the icon looks like this:</span></span>

  ![Outlook용 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="a2b88-142">웹에서 Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-142">In Outlook on the web, the icon looks like this:</span></span>

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="a2b88-144">추가 기능을 사용하는 방법에 대한 자세한 내용은 보고서 메시지 추가 [기능 사용 을 참조합니다.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="a2b88-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="a2b88-145">조직에 대한 보고서 메시지 추가 기능 확인 및 사용</span><span class="sxs-lookup"><span data-stu-id="a2b88-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="a2b88-146">추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="a2b88-147">Microsoft 365 관리 센터에서 **설정,** 통합 앱 및 추가 & 페이지로 이동한 다음 추가 기능 배포를 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-147">In the Microsoft 365 admin center, go to the **Settings, integrated Apps & Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="a2b88-149">새 **추가** 기능 플라이아웃이 나타나면 정보를 검토하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="a2b88-150">다음 페이지에서 스토어에서 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-150">On the next page, click **Choose from the Store**.</span></span>

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="a2b88-152">나타나는 **추가 기능** 선택 페이지에서 검색 상자를  클릭하고 보고서 **메시지를** 입력한 다음 검색 **아이콘을** ![ ](../../media/search-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="a2b88-153">결과 목록에서 보고서 메시지를 **찾은** 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![추가 기능 검색 결과 선택](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="a2b88-155">나타나는 대화 상자에서 라이선스 및 개인 정보 정보를 검토하고 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="a2b88-156">나타나는 **추가 기능 구성** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a2b88-157">**할당된 사용자:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="a2b88-158">**모든** 사용자(기본값)</span><span class="sxs-lookup"><span data-stu-id="a2b88-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="a2b88-159">**특정 사용자/그룹**</span><span class="sxs-lookup"><span data-stu-id="a2b88-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="a2b88-160">**저뿐이에요**</span><span class="sxs-lookup"><span data-stu-id="a2b88-160">**Just me**</span></span>

   - <span data-ttu-id="a2b88-161">**배포 방법:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="a2b88-162">**고정(기본값)**: 추가 기능을 지정된 사용자에게 자동으로 배포하며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="a2b88-163">**사용** 가능: 사용자가 홈 추가 기능 **관리에서** 추가 기능을 \> **설치할** \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="a2b88-164">**선택** 사항: 추가 기능을 지정된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![추가 기능 페이지 구성](../../media/configure-add-in.png)

   <span data-ttu-id="a2b88-166">완료되면 배포를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="a2b88-167">보고서 **메시지** 배포 페이지가 나타나면 진행률 보고서와 추가 기능 배포 확인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="a2b88-168">정보를 읽은 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-168">After you read the information, click **Next**.</span></span>

   ![보고서 메시지 배포 페이지](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="a2b88-170">추가 **기능** 발표 페이지가 나타나면 정보를 검토하고 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2b88-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![추가 기능 페이지 발표](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="a2b88-172">보고서 메시지 추가 기능을 사용하는 방법 확인</span><span class="sxs-lookup"><span data-stu-id="a2b88-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="a2b88-173">추가 기능을 할당한 사용자에게는 다음 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="a2b88-174">Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-174">In Outlook, the icon looks like this:</span></span>

  ![Outlook용 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="a2b88-176">웹에서 Outlook에서 아이콘은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-176">In Outlook on the web, the icon looks like this:</span></span>

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="a2b88-178">보고서 메시지 추가 기능을 사용자에게 알릴 때 보고서 메시지 추가 기능을 사용하기 위해 링크를 [포함합니다.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="a2b88-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="a2b88-179">보고서 메시지 추가 기능의 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="a2b88-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="a2b88-180">Microsoft 365 관리 센터에서 서비스 & **추가** 기능 페이지로 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![새 Microsoft 365 Add-Ins 서비스 및 서비스 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="a2b88-182">보고서 메시지 **추가** 기능을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="a2b88-183">나타나는 **보고서 메시지** 편집 플라이아웃에서 조직에 적합한 설정을 검토하고 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="a2b88-184">작업을 마친 후 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-184">When you're finished, click **Save**.</span></span>

   ![보고서 메시지 추가 기능 설정](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="a2b88-186">보고된 메시지 보기 및 검토</span><span class="sxs-lookup"><span data-stu-id="a2b88-186">View and review reported messages</span></span>

<span data-ttu-id="a2b88-187">사용자가 Microsoft에 보고하는 메시지를 검토하기 위해 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="a2b88-188">관리 제출 포털을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a2b88-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="a2b88-189">자세한 내용은 Microsoft에 대한 사용자 [제출 보기를 참조하세요.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="a2b88-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="a2b88-190">메일 흐름 규칙(전송 규칙)을 만들어 보고된 메시지의 복사본을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b88-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="a2b88-191">자세한 내용은 메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고하는 사항을 [참조하세요.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="a2b88-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
