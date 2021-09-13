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
description: 다음 단계에 따라 기본 이동성 및 보안 문제를 추적합니다.
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185003"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>기본 이동성 및 보안 문제 해결

기본 모바일 및 보안에서 장치를 등록하려고 할 때 문제가 발생하면 여기에 있는 단계를 수행하여 문제를 추적해 하세요. 일반적인 단계로 문제가 해결되지 않는 경우 장치 유형에 대한 특정 단계가 있는 이후 섹션 중 하나를 참조하세요.

## <a name="steps-to-try-first"></a>먼저 시도하는 단계

시작을 위해 다음을 검사합니다.

- 장치가 Intune과 같은 다른 모바일 장치 관리 공급자에 아직 등록되어 있지 않은지 확인합니다.

- 장치가 올바른 날짜 및 시간으로 설정되어 있는지 확인합니다.

- 디바이스의 다른 WIFI 또는 셀룰러 네트워크로 전환합니다.

- Android 또는 iOS 장치의 경우 디바이스에서 Intune 회사 포털 앱을 제거하고 다시 설치합니다. 

## <a name="ios-phone-or-tablet"></a>iOS 휴대폰 또는 태블릿

- APNS 인증서를 설정해야 합니다. 자세한 내용은 iOS 장치에 [대한 APNs 인증서 만들기를 참조하세요.](create-an-apns-certificate-for-ios-devices.md)

- 일반 **설정(또는** 장치 관리)에서 관리 프로필이 아직 설치되어   >  ****   >  **** 있지 않은지 확인합니다. 있는 경우 제거합니다.

- "디바이스를 등록하지 못했습니다."라는 오류 메시지가 표시될 경우 Microsoft 365 로그인하고 Exchange Online 라이선스가 장치에 로그인된 사용자에게 할당되어 있는지 확인합니다.

- "프로필을 설치하지 못했습니다."라는 오류 메시지가 표시면 다음 중 하나를 시도해 봐야 합니다.

    - Safari가 장치의 기본 브라우저이고 쿠키가 사용하지 않도록 설정되어 있지 않은지 확인합니다.

    - 장치를 다시부팅한 다음 장치로 portal.manage.microsoft.com. 사용자 ID 및 Microsoft 365 사용하여 로그인하고 프로필을 수동으로 설치합니다.

## <a name="windows-rt"></a>Windows RT

- 기본 이동성 및 보안과 함께 작동하려면 도메인이 Microsoft 365 설정되어 있는지 확인 자세한 내용은 기본 이동성 및 [보안 설정 을 참조하세요.](set-up.md)
    
- 참가를 선택하는 대신 사용자가 **켜기**   를 선택해야 **합니다.**

## <a name="windows-10-pc"></a>Windows 10 PC

- 기본 이동성 및 보안과 함께 작동하려면 도메인이 Microsoft 365 설정되어 있는지 확인 자세한 내용은 기본 이동성 및 [보안 설정 을 참조하세요.](set-up.md)
    
- 등록이 Azure Active Directory Premium 않은 경우 사용자가 장치 관리에서 **** 등록을 선택하지 않고 장치 관리에만 등록을 선택해야    **커넥트.**

## <a name="android-phone-or-tablet"></a>Android 휴대폰 또는 태블릿

- 장치가 Android 4.4 이상을 실행 중인지 확인합니다.

- Chrome이 최신 버전이고 기본 브라우저로 설정되어 있는지 확인

- "이 장치를 등록할 수 없습니다."라는 오류 메시지가 표시될 경우 Microsoft 365 로그인하고 Exchange Online 포함된 라이선스가 장치에 로그인한 사용자에게 할당되어 있는지 확인합니다.

- 디바이스의 알림 영역을 확인하여 필요한 최종 사용자 작업이 보류 중인지 확인하고, 보류 중인 경우 작업을 완료합니다.