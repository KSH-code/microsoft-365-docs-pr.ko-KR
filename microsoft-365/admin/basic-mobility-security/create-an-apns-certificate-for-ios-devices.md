---
title: IOS 장치용 APNs 인증서 만들기
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
description: 기본 이동성 및 보안을 통해 iOS 장치를 관리 합니다.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337023"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>IOS 장치용 APNs 인증서 만들기

기본 이동성 및 보안의 Ipad 및 Iphone와 같은 iOS 장치를 관리 하려면 APNs 인증서를 만듭니다.

1. 전역 관리자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.
    
2. 브라우저에서를 입력  [https://protection.office.com](https://protection.office.com/) 합니다.
    
3.  **데이터 손실 방지**   >  **장치 관리**를 선택 하 고 **iOS 장치용 APNs 인증서**를 선택 합니다.    

4. Apple 푸시 알림 인증서 설정 페이지에서 **다음**을 선택 합니다.
    
5. CSR 파일 다운로드를 선택 하 고 사용자 컴퓨터의 원하는 위치에 인증서 서명 요청을 저장 합니다.   **다음**을 선택 합니다.
    
6. APNs 인증서 만들기 페이지에서 다음을 수행 합니다.  

    1. Apple APNS Portal을 선택 하 여 Apple Push Certificate Portal을 엽니다.
    
    2. Sign in with an Apple ID.   

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3.   **인증서 만들기**   및 사용 약관에 동의를 선택 합니다.
    
    4. Microsoft 365에서 컴퓨터로 다운로드 한 인증서 서명 요청으로 이동한 후 **업로드**를 선택 합니다.
    
        Apple Push Certificate Portal에서 만든 APNs 인증서를 컴퓨터로 다운로드 합니다.
    
       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365로 돌아가서 **다음**   을 선택 하 여  **APNS 인증서 업로드**   페이지로 이동 합니다.
    
8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
9.   **마침을**선택 합니다.
    
설치를 완료 하려면 security & 준수 센터 > **보안 정책**   >  **장치 관리**   >  **설정 관리**로 이동 합니다.
