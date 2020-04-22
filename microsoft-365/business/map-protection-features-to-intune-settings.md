---
title: Microsoft 365 Business Premium의 보호 기능을 Intune 설정에 매핑하는 방법
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Microsoft 365 Business Premium의 보호 기능을 Intune 설정에 대해 알아봅니다. 구독은 Intune 설정을 수정할 수 있는 라이선스를 제공 합니다.
ms.openlocfilehash: 572d3364e465067536e8369b49404d3d1de1bb5b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633246"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Microsoft 365 Business Premium의 보호 기능을 Intune 설정에 매핑하는 방법

## <a name="android-and-ios-application-protection-settings"></a>Android 및 iOS 응용 프로그램 보호 설정

다음 표에서는 Android 및 iOS 응용 프로그램 정책 설정을 Intune 설정에 매핑하는 방법을 보여 줍니다.
  
Intune 설정을 찾으려면 Microsoft 365 Business Premium 관리자 자격 증명으로 로그인 하 고 **관리 센터로**이동한 후 **intune**으로 이동 합니다.
  
 > [!IMPORTANT]
 > 
 > Microsoft 365 Business Premium subscription은 모든 Intune 설정을 수정할 수 있는 라이선스를 제공 합니다. [시작 하려면 Intune 소개를 참조 하세요.](https://docs.microsoft.com/intune/introduction-intune)
  
예를 들어, Android &mdash; &mdash; 용 응용 프로그램 정책에서 원하는 정책 이름을 선택한 다음 **정책 설정을**선택 합니다.
  
**장치를 분실하거나 도난당한 경우 작업 파일 보호**에서
  
|**Android 또는 iOS 응용 프로그램 정책 설정**|**Intune 설정**|
|:-----|:-----|
|다음 기간이 지난 후 비활성 장치에서 작업 파일 삭제  <br/> |앱 데이터를 지우기 전 오프라인 간격(일)  <br/> |
|사용자가 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용  <br/> 비즈니스용 OneDrive만 허용됩니다.  <br/> |회사 데이터를 저장할 수 있는 저장소 서비스 선택  <br/> |
|||
   
**사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**에서
  
|**Android 또는 iOS 응용 프로그램 정책 설정**|**Intune 설정**|
|:-----|:-----|
|다음 기간이 지난 후 비활성 장치에서 작업 파일 삭제  <br/> |앱 데이터를 지우기 전 오프라인 간격(일)  <br/> |
|사용자가 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용  <br/> 비즈니스용 OneDrive만 허용됩니다.  <br/> |회사 데이터를 저장할 수 있는 저장소 서비스 선택  <br/> |
|업무 파일 암호화  <br/> |앱 데이터 암호화  <br/> |
|**사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**에서 <br/> ||
|Office 앱 액세스에 PIN 또는 지문 필요  <br/> | 액세스하려면 PIN 필요  <br/>  다음도 설정합니다.  <br/> **단순 PIN 허용**을 **예**로 설정 <br/> **PIN 길이**를 4로 설정  <br/> **PIN 대신 지문 허용**을 **예**로 설정 <br/> **장치 PIN이 관리될 때 앱 PIN을 사용 안 함**을 **아니요**로 설정 <br/> |
|여러 번 로그인이 실패 하는 경우 PIN 다시 설정 (PIN이 필요 하지 않은 경우 비활성화 됨)  <br/> |PIN 다시 설정까지의 입력 시도 횟수  <br/> |
|Office 앱이 유휴 상태인 경우 사용자에 게 다시 로그인 필요 (PIN이 필요 하지 않은 경우 비활성화 됨)  <br/> | 다음 시간(분) 후에 액세스 요구 사항 다시 확인  <br/>  다음도 설정합니다.  <br/> **시간 제한**이 분으로 설정됨  <br/>  Microsoft 365 Business에서 설정한 시간(분)과 동일합니다.  <br/> **오프라인 유예 기간**이 기본적으로 720분으로 설정됨  <br/> |
|탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부  <br/> |무단 해제되거나 루팅된 장치에서 관리되는 앱이 실행되지 않도록 차단  <br/> |
|사용자가 Office 앱의 콘텐츠를 개인 앱으로 복사할 수 있도록 허용  <br/> | 다른 앱에서 잘라내기, 복사 및 붙여넣기 제한  <br/>  Microsoft 365 Business Premium 옵션이 **On**으로 설정 된 경우 다음 세 가지 옵션도 Intune의 **모든 앱** 으로 설정 됩니다.  <br/> **앱에서 다른 앱으로 데이터를 전송할 수 있도록 허용** <br/> **앱에서 다른 앱의 데이터를 받을 수 있도록 허용** <br/> **다른 앱에서 잘라내기, 복사 및 붙여넣기 제한** <br/>  Microsoft 365 Business 옵션을 **On**(켜기)으로 설정하는 경우 모든 Intune 옵션이 다음과 같이 설정됩니다.  <br/> **앱에서 다른 앱으로 데이터를 전송할 수 있도록 허용**이 **정책 관리 앱**으로 설정됨 <br/> **앱에서 다른 앱의 데이터를 받을 수 있도록 허용**이 **모든 앱**으로 설정됨 <br/> **다른 앱에서 잘라내기, 복사 및 붙여넣기 제한**이 **Policy Managed apps with Paste-In**(붙여넣기에 정책 관리된 앱)으로 설정됨 <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 앱 보호 설정

다음 표에서는 Windows 10 응용 프로그램 정책 설정을 Intune 설정에 매핑하는 방법을 보여 줍니다.
  
Intune 설정을 찾으려면 Microsoft 365 Business Premium 관리자 자격 증명으로 로그인 하 고 [Azure 포털로](https://portal.azure.com)이동 합니다. **기타 서비스**를 선택 하 고 **필터**에 Intune을 입력 합니다. **Intune 앱 보호** \> **앱 정책을**선택 합니다.
  
 > [!IMPORTANT]
 >
 >Microsoft 365 Business Premium subscription은 Microsoft 365 Business Premium에서 사용할 수 있는 설정에 매핑되는 Intune 설정만 수정 하는 라이선스를 제공 합니다. 
  
사용 가능한 설정을 탐색 하려면 원하는 정책 이름을 선택한 다음, 왼쪽 탐색 창에서 **일반, 할당**, **허용 앱**, **예외 앱**, **필수 설정**또는 **고급 설정을** 선택 합니다. 
  
|**Windows 10 응용 프로그램 정책 설정**|**Intune 설정**|
|:-----|:-----|
|작업 파일 암호화  <br/> |**고급 설정** \> **데이터 보호**: **등록 취소 시 암호화 키 취소** 및 **Revoke access to protected data device enrolls to MDM**(MDM에 보호된 데이터 장치 등록에 대한 액세스 취소)이 모두 **On**(켜기)으로 설정됩니다.  <br/> |
|사용자가 회사 데이터를 개인 파일로 복사할 수 없도록 합니다.  <br/> |**필수 설정** \> **Windows Information Protection 모드**. **On** Microsoft 365 business premium Maps: **재정의 숨기기**, microsoft 365 Business premium Maps에서 **끄기** : **off**로 설정 합니다.  <br/> |
|Office 문서 액세스 제어  <br/> | 이 설정이 Microsoft 365 Business **Premium에서 설정** 되어 있으면  <br/> 다음 추가 설정과 함께 **고급 설정** \> **액세스**, **Windows에 로그인하는 방법으로 비즈니스용 Windows Hello를 사용합니다.** 가 **On**(켜기)으로 설정됩니다.    <br/> **PIN에 대해 필요한 최소 문자 수를 설정합니다.** 가 **4**로 설정됩니다.    <br/> **비즈니스용 Windows Hello PIN에 대문자 사용을 구성합니다.** 가 **Do not allow use of upper case letters for PIN**(PIN에 대문자 사용 허용 안 함)으로 설정됩니다.    <br/> **비즈니스용 Windows Hello PIN에 소문자 사용을 구성합니다.** 가 **Do not allow use of upper case letters for PIN**(PIN에 소문자 사용 허용 안 함)으로 설정됩니다.    <br/> **비즈니스용 Windows Hello PIN에 특수 문자 사용을 구성합니다.** 가 **PIN에 특수 문자 사용 허용 안 함**으로 설정됩니다.    <br/> **시스템에서 사용자를 변경 하도록 요구 하기 전에 PIN을 사용할 수 있는 기간 (일)** 을 **0**으로 설정 합니다.  <br/> **다시 사용할 수 없는 사용자 계정에 연결할 수 있는 이전 PIN의 숫자를 지정합니다.** 가 **0**으로 설정됩니다.    <br/> **장치가 초기화되기 전 허용되는 인증 실패 횟수**가 Microsoft 365 Business의 설정과 동일하게 설정됩니다(기본적으로 5).  <br/> **장치가 유휴 상태로 전환된 후 장치의 PIN 또는 암호가 잠기게 되는 최대 허용 시간(분)** 이 Microsoft 365 Business의 설정과 동일하게 설정됩니다.  <br/> |
|보호된 데이터의 복구 사용  <br/> |**고급 설정** \> **데이터 보호**: **엔터프라이즈 데이터 보호 아이콘 표시** 및 **WIP에 대해 Azure RMS 사용**이 **On**(켜기)으로 설정됩니다.  <br/> |
|추가 회사 클라우드 위치 보호  <br/> |**고급 설정** \> **도메인 보호** 및 **클라우드 리소스**에서 도메인 및 SharePoint 사이트를 표시합니다.  <br/> |
|이러한 앱에서 사용하는 파일이 보호됨  <br/> |보호된 앱 목록이 **허용된 앱**에 나열됩니다.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 장치 보호 설정

다음 표에서는 Windows 10 장치 구성 설정을 Intune 설정에 매핑하는 방법을 보여 줍니다.
  
Intune 설정을 찾으려면 Microsoft 365 Business Premium 관리자 자격 증명으로 로그인 하 고 [Azure 포털로](https://portal.azure.com)이동한 다음 **추가 서비스**를 선택 하 고 intune을 **필터**에 입력 하 고 **intune** \> **장치 구성** \> **프로필**을 선택 합니다. 그런 다음 **Windows 10에 대한 장치 정책** \> **속성** \> **설정**을 선택합니다.
  
|**Windows 10 장치 정책 설정**|**Intune 설정**|
|:-----|:-----|
|Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원  <br/> |실시간 모니터링 허용 = 켜기  <br/> 클라우드 보호 허용 = 켜기  <br/> 사용자에게 샘플 제출 확인 = 자동으로 안전한 샘플 보내기(기본 비 PII 자동 제출)  <br/> |
|Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원  <br/> |**Edge 브라우저 설정**의 **SmartScreen**이 **필수**로 설정됩니다.  <br/> |
|이 시간 동안 유휴 상태일 때 장치 화면 끄기(분)  <br/> |화면이 잠기기 전까지 최대 비활성 시간(분)  <br/> |
|사용자가 Microsoft Store에서 앱을 다운로드할 수 있도록 허용  <br/> |사용자 지정 URI 정책  <br/> |
|사용자가 Cortana에 액세스할 수 있도록 허용  <br/> |Microsoft 365 Business Premium에서 **off** 로 설정 되 면 Intune에서 **일반** \> **Cortana** 가 **차단** 으로 설정 됩니다.  <br/> |
|사용자가 Microsoft에서 Windows 팁 및 광고를 받을 수 있도록 허용  <br/> |**Windows 추천**, Microsoft 365 Business Premium에서 **off** 로 설정 된 경우 모두 차단 됩니다.  <br/> |
|자동으로 Windows 10 장치를 최신 상태로 유지  <br/> | 이 설정은 **Microsoft Intune** \> **서비스 업데이트-windows 10 업데이트 링**에서 **windows 10 장치에 대 한 업데이트 정책**, **속성** \> **설정을**차례로 선택 합니다.  <br/>  Microsoft 365 Business Premium 설정이 **On**으로 설정 되 면 다음 설정이 모두 설정 됩니다.  <br/> **서비스 분기가** **CB** 로 설정 됩니다 (Microsoft 365 Business Premium에서이 기능을 해제 한 경우 cbb).  <br/> **Microsoft 제품 업데이트**는 **허용**으로 설정됩니다.  <br/> **Windows 드라이버**는 **허용**으로 설정됩니다.  <br/> **자동 업데이트 동작**은 다음 설정과 함께 **유지 관리 시간에 자동 설치**로 설정됩니다.  <br/> **After hours start**(초과 근무 시간 시작)가 **오전 6시**로 설정됩니다.  <br/> **활성 시간 끝**이 **오후 10시**로 설정됩니다.  <br/> **품질 업데이트 지연 기간(일)** 은 **0**으로 설정됩니다.  <br/> **기능 업데이트 지연 기간(일)** 은 **0**으로 설정됩니다.  <br/> **배달 최적화 다운로드 모드**는 **동일한 NAT 뒤의 피어링과 혼합된 HTTP**로 설정됩니다.  <br/> |
|||
   

