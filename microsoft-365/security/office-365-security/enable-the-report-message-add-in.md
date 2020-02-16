---
title: 보고서 메시지 추가 기능을 사용하도록 설정
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
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
ms.openlocfilehash: 94dbe7d9dcd5cf3dc8bd5874550880d813f879f5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086410"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="9e0f4-103">보고서 메시지 추가 기능을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9e0f4-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="9e0f4-104">Outlook 및 웹용 outlook에 대 한 보고서 메시지 추가 기능은 [Outlook 정크 메일 필터](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)와는 완전히 동일 하지는 않지만 전자 메일을 정크로 표시 하거나 정크 메일이 아닌 다른 것으로 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="9e0f4-105">차이점은 Outlook 정크 메일 필터를 사용 하 여 사용자의 사서함에 있는 전자 메일 메시지를 구성 하는 것과는 달리, 웹용 outlook의 보고서 메시지 추가 기능에서 Microsoft에 게 스팸으로 잘못 분류 전자 메일을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span>

## <a name="overview"></a><span data-ttu-id="9e0f4-106">개요</span><span class="sxs-lookup"><span data-stu-id="9e0f4-106">Overview</span></span>

<span data-ttu-id="9e0f4-107">Outlook 및 웹용 Outlook (이전의 Outlook Web App)에 대 한 보고서 메시지 추가 기능을 사용 하면 안전한 지 또는 악의적이 든 관계 없이 스팸으로 잘못 분류 전자 메일을 Microsoft 및 해당 계열사에 쉽게 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-107">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="9e0f4-108">Microsoft는 이러한 전송을 사용 하 여 전자 메일 보호 기술의 효율성을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="9e0f4-109">또한 조직에서 [Office 365 Advanced Threat Protection 계획 1](office-365-atp.md) 또는 [계획 2](office-365-ti.md)를 사용 하는 경우 보고서 메시지 추가 기능은 조직의 보안 팀에 게 보안 정책을 검토 하 고 업데이트 하는 데 사용할 수 있는 유용한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="9e0f4-110">예를 들어 사용자가 많은 양의 메시지를 피싱 메일로 보고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="9e0f4-111">이 정보는 [보안 대시보드](security-dashboard.md) 및 기타 보고서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="9e0f4-112">조직의 보안 팀에서이 정보를 사용 하 여 피싱 방지 정책을 업데이트 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="9e0f4-113">또는 사용자가 보고서 메시지 추가 기능을 사용 하 여 정크 메일로 플래그를 지정 하지 않은 많은 메시지를 보고 하는 경우 조직의 보안 팀이 [스팸 방지 정책을](configure-the-anti-spam-policies.md)조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

<span data-ttu-id="9e0f4-114">보고서 메시지 추가 기능 이란 대부분의 Office 365 구독과 다음 제품과 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-114">The Report Message add-in works with most Office 365 subscriptions and the following products:</span></span>

 - <span data-ttu-id="9e0f4-115">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="9e0f4-115">Outlook on the web</span></span>
 - <span data-ttu-id="9e0f4-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="9e0f4-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="9e0f4-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9e0f4-117">Outlook 2016</span></span>
 - <span data-ttu-id="9e0f4-118">Mac용 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9e0f4-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="9e0f4-119">Office 365 ProPlus에 포함 된 Outlook</span><span class="sxs-lookup"><span data-stu-id="9e0f4-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="9e0f4-120">보고서 메시지 추가 기능은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-120">The Report Message add-in is currently not available for:</span></span>

 - <span data-ttu-id="9e0f4-121">온-프레미스 Exchange 조직의 사서함</span><span class="sxs-lookup"><span data-stu-id="9e0f4-121">Mailboxes in on-premises Exchange organizations</span></span>
 - <span data-ttu-id="9e0f4-122">GCC, GCC HIGH 또는 DoD 구독</span><span class="sxs-lookup"><span data-stu-id="9e0f4-122">GCC, GCC HIGH, or DoD subscriptions</span></span>

<span data-ttu-id="9e0f4-123">기존 웹 브라우저는 보고서 메시지 추가 기능을 사용 하기에 충분 해야 합니다. 그러나 추가 기능이 사용 가능 하지 않거나 예상 대로 작동 하지 않는 경우 다른 브라우저를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-123">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

<span data-ttu-id="9e0f4-124">개별 사용자 [의 경우에는 보고서 메시지 추가 기능을 사용 하도록 설정할](#get-the-report-message-add-in-for-yourself)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-124">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="9e0f4-125">Office 365 전역 관리자 또는 Exchange Online 관리자이 고 Exchange가 OAuth 인증을 사용 하도록 구성 되어 있는 경우 [조직에 대 한 보고서 메시지 추가 기능을 사용 하도록 설정할](#get-and-enable-the-report-message-add-in-for-your-organization)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-125">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="9e0f4-126">이제 [중앙 집중식 배포](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)를 통해 보고서 메시지 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-126">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="9e0f4-127">사용자를 위한 보고서 메시지 추가 기능 가져오기</span><span class="sxs-lookup"><span data-stu-id="9e0f4-127">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="9e0f4-128">[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)에서 [보고서 메시지 추가 기능](https://appsource.microsoft.com/product/office/wa104381180)을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-128">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>

2. <span data-ttu-id="9e0f4-129">**지금 다운로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-129">Choose **GET IT NOW**.</span></span>

   ![메시지 보고-지금 받기](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="9e0f4-131">사용 약관 및 개인 정보 보호 정책을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-131">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="9e0f4-132">그런 다음 **계속**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-132">Then choose **Continue**.</span></span>

4. <span data-ttu-id="9e0f4-133">회사 또는 학교 계정 (비즈니스용 사용) 또는 Microsoft 계정 (개인적으로 사용)을 사용 하 여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-133">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="9e0f4-134">추가 기능을 설치 하 고 사용 하도록 설정한 후에는 다음 아이콘이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-134">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="9e0f4-135">Outlook에서 아이콘은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-135">In Outlook, the icon looks like this:</span></span>

  ![Outlook에 대 한 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="9e0f4-137">웹용 Outlook (이전의 Outlook Web App)에서는 아이콘이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-137">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span>

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="9e0f4-139">다음 단계에서는 [보고서 메시지 추가 기능을 사용](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-139">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="9e0f4-140">조직에 대 한 보고서 메시지 추가 기능 가져오기 및 사용</span><span class="sxs-lookup"><span data-stu-id="9e0f4-140">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e0f4-141">이 작업을 완료 하려면 Office 365 전역 관리자 또는 Exchange Online 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-141">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="9e0f4-142">또한 OAuth 인증을 사용 하 여 자세한 내용을 확인할 수 있도록 Exchange를 구성 해야 합니다. [exchange 요구 사항 (추가 기능의 중앙 집중식 배포)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-142">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

1. <span data-ttu-id="9e0f4-143">Microsoft 365 관리 센터의 [서비스 & 추가 기능 페이지로](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-143">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![새 Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="9e0f4-145">**+ 배포 추가 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-145">Choose **+ Deploy Add-in**.</span></span>

   ![배포 추가 기능 선택](../../media/ServicesAddIns-ChooseDeployAddIn.png)

3. <span data-ttu-id="9e0f4-147">**새 추가 기능** 화면에서 정보를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-147">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span>

   ![새 추가 기능 세부 정보](../../media/NewAddInScreen1.png)

4. <span data-ttu-id="9e0f4-149">**Office 스토어에서 추가 기능을 추가**하려는 경우를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-149">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span>

   ![새 추가 기능을 추가 하려는 경우](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="9e0f4-151">**보고서 메시지**를 검색 하 고 결과 목록에서 **보고서 메시지 추가 기능**옆에 있는 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-151">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span>

   ![보고서 메시지를 검색 하 고 추가를 선택 합니다.](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="9e0f4-153">**보고서 메시지** 화면에서 정보를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-153">On the **Report Message** screen, review the information, and then choose **Next**.</span></span>

   ![보고서 메시지 정보](../../media/ReportMessageAdd-InNewScreen4.png)

7. <span data-ttu-id="9e0f4-155">Outlook에 대 한 사용자 기본 설정을 지정 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-155">Specify the user default settings for Outlook, and  then choose **Next**.</span></span>

   ![Outlook에 대 한 메시지 기본 설정](../../media/ReportMessageOptionsScreen5.png)

8. <span data-ttu-id="9e0f4-157">보고서 메시지 추가 기능을 가져오는 사용자를 지정한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-157">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span>

   ![보고서 메시지 추가 기능을 가져오는 사람](../../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> <span data-ttu-id="9e0f4-159">[사용자가 보고 하는 전자 메일 메시지의 복사본을 가져오기 위한 규칙을 설정 하는](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-159">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="9e0f4-160">추가 기능을 설정할 때 선택한 사항 (위의 7-8 단계)에 따라 조직의 사용자가 [보고서 메시지 추가 기능](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-160">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="9e0f4-161">조직의 사용자에 게 다음 아이콘이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-161">People in your organization will see the following icons:</span></span>

- <span data-ttu-id="9e0f4-162">Outlook에서 아이콘은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-162">In Outlook, the icon looks like this:</span></span>

  ![Outlook에 대 한 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="9e0f4-164">웹용 Outlook에서 아이콘은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-164">In Outlook on the web, the icon looks like this:</span></span>

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="9e0f4-166">사용자에 게 보고서 메시지 추가 기능에 대 한 알림을 보내는 경우 [보고서 메시지 추가 기능을 사용](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)하는 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-166">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="9e0f4-167">사용자가 보고 하는 전자 메일 메시지의 복사본을 가져오기 위한 규칙 설정</span><span class="sxs-lookup"><span data-stu-id="9e0f4-167">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e0f4-168">이 작업을 수행 하려면 Exchange Online 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-168">You must be an Exchange Online Administrator to perform this task.</span></span>

<span data-ttu-id="9e0f4-169">조직의 사용자가 보고 하는 전자 메일 메시지의 복사본을 가져오기 위한 규칙을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-169">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="9e0f4-170">조직에 대 한 보고서 메시지 추가 기능을 다운로드 하 고 사용 하도록 설정한 후이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-170">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>

1. <span data-ttu-id="9e0f4-171">Exchange 관리 센터에서 **메일 흐름** \> **규칙**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-171">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span>

2. <span data-ttu-id="9e0f4-172">**+** \> **새 규칙 만들기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-172">Choose **+** \> **Create a new rule**.</span></span>

3. <span data-ttu-id="9e0f4-173">**이름** 상자에 제출을 비롯 한 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-173">In the **Name** box, type a name, such as Submissions.</span></span>

4. <span data-ttu-id="9e0f4-174">다음의 **경우이 규칙 적용** 목록에서 **받는 사람 주소에 다음 포함 ...** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-174">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span>

5. <span data-ttu-id="9e0f4-175">**단어 또는 구 지정** 화면에서을 추가 `junk@office365.microsoft.com` `phish@office365.microsoft.com`하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-175">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span>

   ![규칙에 대 한 정크 및 피싱 전자 메일 주소 지정](../../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. <span data-ttu-id="9e0f4-177">**다음 작업 수행** ... 목록에서 **숨은 참조 메시지를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-177">In the **Do the following...** list, choose **Bcc the message to...**.</span></span>

7. <span data-ttu-id="9e0f4-178">사용자가 Microsoft에 보고 하는 각 전자 메일 메시지의 복사본을 받아야 하는 전역 관리자, 보안 관리자 및/또는 보안 리더를 추가한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-178">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span>

   ![전역 또는 보안 관리자를 추가 하 여 보고 된 각 메시지의 복사본을 수신 합니다.](../../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. <span data-ttu-id="9e0f4-180">**심각도 수준으로이 규칙 감사**를 선택 하 고 **중간**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-180">Select **Audit this rule with severity level**, and choose **Medium**.</span></span>

9. <span data-ttu-id="9e0f4-181">**이 규칙에 대 한 모드 선택**에서 **적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-181">Under **Choose a mode for this rule**, choose **Enforce**.</span></span>

   ![보고 된 각 메시지의 복사본을 가져오기 위한 규칙 설정](../../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. <span data-ttu-id="9e0f4-183">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-183">Choose **Save**.</span></span>

<span data-ttu-id="9e0f4-184">이 규칙을 적용 하면 조직의 누군가가 보고서 메시지 추가 기능을 사용 하 여 전자 메일 메시지를 보고할 때마다 전역 관리자, 보안 관리자 및/또는 보안 판독기가 해당 메시지의 복사본을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-184">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="9e0f4-185">이 정보를 사용 하 여 [Office 365 ATP 안전한 링크](atp-safe-links.md) 정책 또는 [스팸 방지](anti-spam-protection.md) 설정 등의 정책을 설정 하거나 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-185">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span>

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="9e0f4-186">보고서 메시지 추가 기능을 사용 하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="9e0f4-186">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="9e0f4-187">[보고서 메시지 추가 기능 사용](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-187">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="9e0f4-188">보고서 메시지 추가 기능의 설정 검토 또는 편집</span><span class="sxs-lookup"><span data-stu-id="9e0f4-188">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="9e0f4-189">[서비스 & 추가 기능 페이지](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)에서 보고서 메시지 추가 기능의 기본 설정을 검토 하 고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-189">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e0f4-190">이 작업을 완료 하려면 Office 365 전역 관리자 또는 Exchange Online 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-190">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="9e0f4-191">Microsoft 365 관리 센터의 [서비스 & 추가 기능 페이지로](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-191">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![새 Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="9e0f4-193">보고서 메시지 추가 기능을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-193">Find and select the Report Message add-in.</span></span>

   ![보고서 메시지 추가 기능 찾기 및 선택](../../media/FindReportMessageAddIn.png)

3. <span data-ttu-id="9e0f4-195">보고서 메시지 화면에서 조직에 적합 한 설정을 검토 하 고 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0f4-195">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span>

   ![보고서 메시지 추가 기능에 대 한 설정](../../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a><span data-ttu-id="9e0f4-197">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9e0f4-197">Related topics</span></span>

[<span data-ttu-id="9e0f4-198">보고서 메시지 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="9e0f4-198">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[<span data-ttu-id="9e0f4-199">보안 &amp; 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="9e0f4-199">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="9e0f4-200">Office 365 Advanced Threat Protection에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="9e0f4-200">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="9e0f4-201">보안 &amp; 및 준수 센터에서 탐색기 사용</span><span class="sxs-lookup"><span data-stu-id="9e0f4-201">Use Explorer in the Security &amp; Compliance Center</span></span>](threat-explorer.md)
