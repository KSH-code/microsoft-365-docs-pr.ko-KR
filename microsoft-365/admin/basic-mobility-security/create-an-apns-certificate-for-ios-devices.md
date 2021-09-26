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
ms.custom: AdminSurgePortfolio
description: 기본 모바일 및 보안에서 iOS 장치를 관리합니다.
ms.openlocfilehash: c7fa6a83690483d5e3b286688f4d6ed46495b096
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59773910"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>iOS 장치용 APN 인증서 만들기

iPad 및 iPhone과 같은 iOS 장치를 기본 모바일 및 보안에서 관리하기 위해 APNS 인증서를 만드십시오.

1. 전역 관리자 Microsoft 365 로그인합니다.

2. 브라우저에 를  <https://protection.office.com/> 입력합니다.

3. 데이터  **손실 방지 장치** 관리   >  **를 선택하고** iOS 장치에 대한 **APNs 인증서를 선택합니다.**

4. Apple 푸시 알림 인증서 설정 페이지에서 다음 을 **선택합니다.**

5. CSR 파일 다운로드를 선택하고 인증서 서명 요청을 기억할 컴퓨터의 어느 곳에나 저장합니다. 다음  **을 선택합니다.**

6. APNs 인증서 만들기 페이지에서 다음을 클릭합니다.

    1. Apple APNS 포털을 선택하여 Apple Push 인증서 포털을 열 수 있습니다.

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. 인증서  **만들기를 선택하고**   사용 약관에 동의합니다.

    4. 에서 컴퓨터에 다운로드한 인증서 서명 요청으로 Microsoft 365 를 **업로드.**

       Apple Push Certificate Portal에서 만든 APNS 인증서를 컴퓨터에 다운로드합니다.

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. 다시 Microsoft 365 다음을 선택하여 업로드    인증서  **페이지로**   이동합니다.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. 마친  **을 선택합니다.**

설치를 완료하려면 보안 정책 & 관리 센터로 > **관리**   >  ****   >  **설정으로 이동합니다.**
