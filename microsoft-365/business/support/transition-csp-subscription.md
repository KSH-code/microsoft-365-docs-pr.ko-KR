---
title: Microsoft 365 Business CSP 구독을 전환
description: Microsoft 365 Business CSP 구독을 미리 보기에서 GA (일반 가용성)으로 전환 하는 방법에 대해 알아봅니다.
author: jasongroce
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-mar
- AdminSurgePortfolio
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365, SMB, CSP 구독 전환
ms.date: 11/01/2017
ms.openlocfilehash: 5fc532b4a59d8e94068e7e1bae99bf8edac75abb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403433"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Microsoft 365 Business CSP 구독을 전환

Microsoft 365 Business 미리 보기 CSP를 구독 중인 경우 이 가이드를 따라 기존 미리 보기 구독을 Microsoft 365 Business GA(일반 가용성)으로 전환하는 방법을 알아보세요.

**미리 보기 구독을 GA로 전환하는 방법**

1. <a href="https://partnercenter.microsoft.com" target="_blank">파트너 센터</a>에 로그인 합니다.
2. 대시보드에서 **고객**을 선택한 다음 회사 이름을 찾아 선택합니다.

    회사의 구독이 나열됩니다.

    ![파트너 센터의 고객 구독](../../media/pc_customer_subscriptions_1.png)
    
3. 회사의 **구독** 페이지에서 **구독 추가**를 선택 합니다.
4. **새 구독** 페이지에서 **Small business** 을 선택한 다음 목록에서 **Microsoft 365 business** 를 선택 합니다.
5. 라이선스 수를 추가하고 **다음: 검토**를 선택하여 구독을 검토한 다음 **제출**을 선택합니다.

    ![Microsoft 365 Business에 대한 새 구독을 검토](../../media/pc_customer_reviewnewsubscription.png)

    **라이선스 기준 구독**에 **Microsoft 365 Business 미리 보기** 및 **Microsoft 365 Business**가 표시됩니다. 다음에 미리 보기 구독을 일시 중단 합니다.

6. **Microsoft 365 Business 미리 보기**를 선택합니다.
7. **Microsoft 365 Business Preview** 페이지에서 **일시 중단** 을 선택 하 여 미리 보기 구독을 일시 중단 합니다.

    ![Microsoft 365 Business 미리 보기 구독 일시 중단](../../media/pc_customer_m365bpreview_suspend.png)

8. **제출**을 선택하여 확인합니다.

    **구독** 페이지에서 **Microsoft 365 Business Preview** 상태가 **일시 중단**으로 표시 되는지 확인 합니다.

    ![미리 보기 구독이 일시 중단되었는지 확인](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. 필요에 따라 라이선스 계약을 확인할 수도 있습니다. 이렇게 하려면 다음 단계를 따르세요.
    1. 회사의 **구독** 페이지에서 **사용자 및 라이선스**를 선택합니다.
    2. **사용자 및 라이선스** 페이지에서 사용자를 선택 합니다.
    3. 사용자의 페이지에서 **라이선스 할당** 섹션을 선택 하 여 **Microsoft 365 Business**가 표시 되는지 확인 합니다.

        ![Microsoft 365 Business 라이선스가 사용자에게 할당되었는지 확인](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>전환 도중 및 이후 고객과 사용자에게 미치는 영향

전환과 사후 전환 중에는 고객과 사용자에 게 영향을 주지 않습니다.

## <a name="impact-to-customers-who-dont-transition"></a>전환하지 않은 고객에 미치는 영향

다음 표에는 Microsoft 365 Business 미리 보기 구독을 Microsoft 365 Business 구독으로 전환하지 않은 고객에 미치는 영향이 요약되어 있습니다.

|       | T-0 ~ T+30     | T+30 ~ T+60 | T+60 ~ T+120 | T+120 이상  |
|-------|-----------------|--------------|---------------|---------------|
| **상태** | 유예 기간 | 만료됨      | 사용 안 함      | 프로비전 해제됨 |
| **서비스 영향**                                                        |
| **Microsoft 365 Business 관리 포털** | 기능에 미치는 영향은 없음 | 기능에 미치는 영향은 없음 | 사용자를 추가/삭제하고, 구독을 구매할 수 있습니다.</br> 라이선스를 할당/해지할 수 없습니다. | 고객의 구독 및 모든 데이터가 삭제됩니다. 관리자는 다른 유료 구독을 관리할 수 있습니다. |
| **Office 앱**                         | 최종 사용자 영향 없음 | 최종 사용자 영향 없음 | Office는 제한된 기능 모드로 전환됩니다.</br> 사용자는 파일만 볼 수 있습니다. | Office는 제한된 기능 모드로 전환됩니다.</br> 사용자는 파일만 볼 수 있습니다. |
| **클라우드 서비스(SharePoint Online, Exchange Online, Skype, Teams 등)** | 최종 사용자 영향 없음 | 최종 사용자 영향 없음 | 최종 사용자 및 관리자가 클라우드에서 데이터에 액세스할 수 없습니다. | 고객의 구독 및 모든 데이터가 삭제됩니다. |
| **EM+S 구성 요소** | 관리자 영향 없음</br> 최종 사용자 영향 없음 | 관리자 영향 없음</br> 최종 사용자 영향 없음 | 기능이 더 이상 적용 되지 않습니다.</br> 자세한 내용은 [구독 만료 시 모바일 장치 영향](#mobile-device-impacts-upon-subscription-expiration) 및 [구독 만료 시 Windows 10 PC 영향](#windows-10-pc-impacts-upon-subscription-expiration)을 참조하십시오. | 기능이 더 이상 적용 되지 않습니다.</br> 자세한 내용은 [구독 만료 시 모바일 장치 영향](#mobile-device-impacts-upon-subscription-expiration) 및 [구독 만료 시 Windows 10 PC 영향](#windows-10-pc-impacts-upon-subscription-expiration)을 참조하십시오. |
| **Windows 10 Business** | 관리자 영향 없음</br> 최종 사용자 영향 없음 | 관리자 영향 없음</br> 최종 사용자 영향 없음 | 기능이 더 이상 적용 되지 않습니다.</br> 자세한 내용은 [구독 만료 시 모바일 장치 영향](#mobile-device-impacts-upon-subscription-expiration) 및 [구독 만료 시 Windows 10 PC 영향](#windows-10-pc-impacts-upon-subscription-expiration)을 참조하십시오. | 기능이 더 이상 적용 되지 않습니다.</br> 자세한 내용은 [구독 만료 시 모바일 장치 영향](#mobile-device-impacts-upon-subscription-expiration) 및 [구독 만료 시 Windows 10 PC 영향](#windows-10-pc-impacts-upon-subscription-expiration)을 참조하십시오. |
| **Windows 10 PC에 대한 Azure AD 로그인** | 관리자 영향 없음</br> 최종 사용자 영향 없음 | 관리자 영향 없음</br> 최종 사용자 영향 없음 | 관리자 영향 없음</br> 최종 사용자 영향 없음 | 테 넌 트가 삭제 되 면 사용자는 로컬 자격 증명만 사용 하 여 로그인 할 수 있습니다. 로컬 자격 증명이 없는 경우 이미지로 장치를 다시 설치합니다. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>구독 만료 시 모바일 장치 영향

다음 표에는 모바일 장치에 대 한 앱 관리 정책에 대 한 영향이 요약 되어 있습니다.

|                            | 완전히 사용이 허가된 환경                      | 만료 후 T+60일          |
|----------------------------|------------------------------------------------|------------------------------------|
| **비활성 장치에서 작업 파일을 삭제** | 선택한 기간(일) 후 작업 파일이 젝거됩니다. | 작업 파일이 사용자의 개인 장치에 유지됩니다. |
| **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** | 작업 파일을 비즈니스용 OneDrive에만 저장할 수 있습니다. | 작업 파일을 어디에나 저장할 수 있습니다. |
| **작업 파일 암호화** | 작업 파일이 암호화됩니다. | 더 이상 작업 파일이 암호화되지 않습니다.</br> 보안 정책이 제거되고 앱에서 Office 데이터가 제거됩니다. |
| **Office 앱에 액세스하려면 PIN 또는 지문 필요** | 앱에 대한 액세스가 제한됩니다. | 앱 수준의 액세스 제한이 없습니다. |
| **로그인 실패 시 PIN을 다시 설정** | 앱에 대한 액세스가 제한됩니다. | 앱 수준의 액세스 제한이 없습니다. |
| **Office 앱이 유휴 상태 전환 후 사용자에게 다시 로그인하도록 요구** | 로그인이 필요합니다. | 로그인 필요 없음 |
| **무단 해제 또는 루팅된 장치에 있는 작업 파일에 액세스 거부** | 탈 옥/루 팅 된 장치에서 작업 파일에 액세스할 수 없음 | 무단 해제 또는 루팅된 장치에 있는 작업 파일에 액세스할 수 있습니다. |
| **사용자가 Office 앱에서 개인 앱으로 콘텐츠를 복사하도록 허용** | Microsoft 365 구독의 일부로 사용할 수 있는 앱에 제한 된 복사/붙여넣기 | 모든 앱에서 복사/붙여 넣기를 사용할 수 있습니다. |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>구독 만료 시 Windows 10 PC 영향

다음 표에는 Windows 10 장치 구성 정책에 대한 영향이 요약되어 있습니다.

|                            | 완전히 사용이 허가된 환경                      | 만료 후 T+60일          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Windows Defender를 사용하여 위협으로부터 PC를 보호** | 켜기/끄기가 사용자 제어에 포함되지 않습니다. | 사용자가 Windows 10 PC에서 Windows Defender를 켜고 끌 수 있습니다. |
| **Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호** | Microsoft Edge에서 PC 보호 | 사용자는 Microsoft Edge에서 PC 보호를 켜고 끌 수 있습니다. |
| **유휴 상태일 때 장치 화면 끄기** | 관리자가 화면 제한 시간 정책을 정의합니다. | 최종 사용자가 화면 제한 시간을 구성할 수 있습니다. |
| **사용자가 Microsoft Store에서 앱을 다운로드하도록 허용** | 사용자가 Microsoft Store에서 앱을 다운로드할 수 있는지 여부를 관리자가 정의합니다. | 사용자가 언제라도 Microsoft Store에서 앱을 다운로드할 수 있습니다. |
| **사용자가 Cortana에 액세스하도록 허용** | 사용자가 Cortana에 액세스할 수 있는지에 대한 정책을 관리자가 정의합니다. | 사용자가 장치에서 Cortana를 켜고 끌 수 있습니다. |
| **사용자가 Microsoft에서 팁과 광고를 수신하도록 허용** | 사용자가 Microsoft로부터 팁과 광고를 수신할 수 있는지에 대한 정책을 관리자가 정의합니다. | 사용자가 Microsoft의 팁 및 광고를 켜고 끌 수 있습니다. |
| **사용자가 Office 앱에서 개인 앱으로 콘텐츠를 복사하도록 허용** | Windows 10 장치를 최신 상태로 유지 하는 정책을 관리자가 정의 합니다. | 사용자가 Windows 업데이트 시기를 결정할 수 있습니다. |
