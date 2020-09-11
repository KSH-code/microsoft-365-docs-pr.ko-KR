---
title: 기본 이동성 및 보안 문제 해결
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
description: 기본 이동성 및 보안 문제를 추적 하려면 다음 단계를 수행 하세요.
ms.openlocfilehash: 43e7533e598f769dd5f2bcae28c4252f96a9be76
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430251"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>기본 이동성 및 보안 문제 해결

기본 Mobility and Security에서 장치를 등록 하려고 할 때 문제가 발생 하는 경우 다음 단계를 수행 하 여 문제를 추적 해 보세요. 일반적인 단계를 수행 해도 문제가 해결 되지 않는 경우에는 해당 디바이스 유형에 대 한 특정 단계를 포함 하는 이후 섹션 중 하나를 참조 하십시오.

## <a name="steps-to-try-first"></a>먼저 시도해 야 할 단계

시작 하려면 다음을 확인 합니다.

- 장치가 Intune과 같은 다른 모바일 장치 관리 공급자에 등록 되어 있지 않은지 확인 합니다.
    
- 장치가 올바른 날짜 및 시간으로 설정 되어 있는지 확인 합니다.
    
- 장치에서 다른 WIFI 또는 셀룰러 네트워크로 전환 합니다.
    
- Android 또는 iOS 장치의 경우 장치에서 Intune 회사 포털 앱을 제거 하 고 다시 설치 합니다. 

## <a name="ios-phone-or-tablet"></a>iOS 전화 또는 태블릿

- APNs 인증서를 설정 했는지 확인 합니다. 자세한 내용은 [iOS 장치용 APNs 인증서 만들기](create-an-apns-certificate-for-ios-devices.md)를 참조 하세요.
    
-  **설정**   >  **일반**   >  **프로필 (또는 장치 관리)** 에서 관리 프로필이 이미 설치 되어 있지 않은지 확인 합니다. 해당 하는 경우 제거 합니다.
    
- "장치를 등록 하지 못했습니다." 라는 오류 메시지가 표시 되 면 Microsoft 365에 로그인 하 여 Exchange Online이 포함 된 라이선스가 장치에 로그인 한 사용자에 게 할당 되었는지 확인 합니다.
    
- "프로필을 설치 하지 못했습니다." 라는 오류 메시지가 표시 되 면 다음 중 하나를 수행 합니다.
    
    - Safari가 장치에서 기본 브라우저이 고 해당 쿠키를 사용 하지 않도록 설정 되어 있는지 확인 합니다.
    
    - 장치를 다시 부팅 한 다음 portal.manage.microsoft.com로 이동 합니다. Microsoft 365 사용자 ID 및 암호를 사용 하 여 로그인 하 고 프로필을 수동으로 설치 해 봅니다.    

## <a name="windows-rt"></a>Windows RT

- 기본 이동성 및 보안을 사용 하려면 도메인이 Microsoft 365에 설정 되어 있는지 확인 합니다. 자세한 내용은 [기본 이동성 및 보안 설정을](set-up.md)참조 하십시오.
    
- 연결을 선택 하는 대신 사용자가 **설정을**선택 하 고 있는지 확인   합니다. **Join**    

## <a name="windows-10-pc"></a>Windows 10 PC

- 기본 이동성 및 보안을 사용 하려면 도메인이 Microsoft 365에 설정 되어 있는지 확인 합니다. 자세한 내용은 [기본 이동성 및 보안 설정을](set-up.md)참조 하십시오.
    
- Azure Active Directory Premium이 없는 경우에는 사용자가 연결을 선택 하는 대신 **장치 관리에서 등록**을 선택 하 고 있는지 확인 합니다   . **Connect**

## <a name="android-phone-or-tablet"></a>Android 휴대폰 또는 태블릿

- 장치가 Android 4.4 이상 버전을 실행 하 고 있는지 확인 합니다.
    
- Chrome이 최신 상태이 고 기본 브라우저로 설정 되어 있는지 확인 합니다.
    
- "이 장치를 등록할 수 없습니다." 라는 오류 메시지가 표시 되 면 Microsoft 365에 로그인 하 여 장치에 로그인 한 사용자에 게 Exchange Online을 포함 하는 라이선스가 할당 되었는지 확인 합니다.
    
- 장치의 알림 영역에서 필요한 최종 사용자 작업이 보류 중인지 확인 하 고, 있는 경우 해당 작업을 완료 합니다.