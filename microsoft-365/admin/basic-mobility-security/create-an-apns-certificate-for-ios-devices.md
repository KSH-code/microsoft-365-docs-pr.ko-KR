---
title: iOS 장치용 APN 인증서 만들기
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 기본 모바일 및 보안에서 iOS 장치를 관리합니다.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877083"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="98d5c-103">iOS 장치용 APN 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="98d5c-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="98d5c-104">iPad 및 iPhone과 같은 iOS 장치를 기본 모바일 및 보안에서 관리하기 위해 APNS 인증서를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="98d5c-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="98d5c-105">전역 관리자 Microsoft 365 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="98d5c-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="98d5c-106">브라우저에 를  [https://protection.office.com](https://protection.office.com/) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="98d5c-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="98d5c-107">데이터  **손실 방지 장치** 관리   >  **를 선택하고** iOS 장치에 대한 **APNs 인증서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98d5c-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="98d5c-108">Apple 푸시 알림 인증서 설정 페이지에서 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98d5c-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="98d5c-109">CSR 파일 다운로드를 선택하고 인증서 서명 요청을 기억할 컴퓨터의 어느 곳에나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98d5c-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="98d5c-110">다음  **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98d5c-110">Select  **Next**.</span></span>

6. <span data-ttu-id="98d5c-111">APNs 인증서 만들기 페이지에서 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98d5c-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="98d5c-112">Apple APNS 포털을 선택하여 Apple Push 인증서 포털을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d5c-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="98d5c-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="98d5c-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="98d5c-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="98d5c-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="98d5c-116">인증서  **만들기를 선택하고**   사용 약관에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="98d5c-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="98d5c-117">에서 컴퓨터에 다운로드한 인증서 서명 요청으로 Microsoft 365 를 **업로드.**</span><span class="sxs-lookup"><span data-stu-id="98d5c-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="98d5c-118">Apple Push Certificate Portal에서 만든 APNS 인증서를 컴퓨터에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="98d5c-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="98d5c-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="98d5c-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="98d5c-120">다시 Microsoft 365 다음을 선택하여 업로드    인증서  **페이지로**   이동합니다.</span><span class="sxs-lookup"><span data-stu-id="98d5c-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="98d5c-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="98d5c-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="98d5c-122">마친  **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98d5c-122">Select  **Finish**.</span></span>

<span data-ttu-id="98d5c-123">설치를 완료하려면 보안 정책 & 관리 센터로 > **관리**   >  \*\*\*\*   >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="98d5c-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
