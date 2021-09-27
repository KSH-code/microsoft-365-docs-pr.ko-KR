---
title: Intune 설정에 매핑되는 Microsoft 365 Business Premium 기능
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Intune 설정에 Microsoft 365 Business Premium 보호 기능이 어떻게 매핑되는지 확인합니다. 구독은 Intune 설정을 수정할 수 있는 라이선스를 제공합니다.
ms.openlocfilehash: c12907d5c50499a987e78403e25ace7bc89f4c79
ms.sourcegitcommit: 34259ec9b6cccc8f6e29808dbe4796d9f72b651b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59933738"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Intune 설정에 매핑되는 Microsoft 365 Business Premium 기능

## <a name="android-and-ios-application-protection-settings"></a>Android 및 iOS 응용 프로그램 보호 설정

다음 표에서는 Android 및 iOS 응용 프로그램 정책 설정을 Intune 설정에 매핑하는 방법을 보여 줍니다.
  
Intune 설정을 찾으면 Microsoft 365 Business Premium 자격 증명으로 로그인하고 관리 센터, **Intune으로 이동하세요.** 
  
 > [!IMPORTANT]
 > 
 > Microsoft 365 Business Premium 구독을 사용하면 모든 Intune 설정을 수정할 수 있는 라이선스가 부여됩니다. 시작을 [위해 Intune 소개를 참조합니다.](/intune/introduction-intune)
  
원하는 정책 이름(예: Android용 응용 프로그램 정책)을 선택한 &mdash; &mdash; 다음 정책 설정을 **선택합니다.**
  
**장치를 분실하거나 도난당한 경우 작업 파일 보호** 에서
  
|**Android 또는 iOS 응용 프로그램 정책 설정**|**Intune 설정**|
|:-----|:-----|
|다음 기간이 지난 후 비활성 장치에서 작업 파일 삭제  <br/> |앱 데이터를 지우기 전 오프라인 간격(일)  <br/> |
|사용자가 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용  <br/> 비즈니스용 OneDrive만 허용됩니다.  <br/> |회사 데이터를 저장할 수 있는 저장소 서비스 선택  <br/> |
|||
   
**사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리** 에서
  
|**Android 또는 iOS 응용 프로그램 정책 설정**|**Intune 설정**|
|:-----|:-----|
|다음 기간이 지난 후 비활성 장치에서 작업 파일 삭제  <br/> |앱 데이터를 지우기 전 오프라인 간격(일)  <br/> |
|사용자가 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용  <br/> 비즈니스용 OneDrive만 허용됩니다.  <br/> |회사 데이터를 저장할 수 있는 저장소 서비스 선택  <br/> |
|작업 파일 암호화  <br/> |앱 데이터 암호화  <br/> |
|**사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리** 에서 <br/> ||
|Office 앱 액세스에 PIN 또는 지문 필요  <br/> | 액세스하려면 PIN 필요  <br/>  다음도 설정합니다.  <br/> **단순 PIN 허용** 을 **예** 로 설정 <br/> **PIN 길이** 를 4로 설정  <br/> **PIN 대신 지문 허용** 을 **예** 로 설정 <br/> **장치 PIN이 관리될 때 앱 PIN을 사용 안 함** 을 **아니요** 로 설정 <br/> |
|로그인이 여러 번 실패할 때 PIN 다시 설정(PIN이 필요하지 않은 경우 이 기능을 사용할 수 없음)  <br/> |PIN 다시 설정까지의 입력 시도 횟수  <br/> |
|앱이 유휴된 후 Office 다시 로그인해야 합니다(PIN이 필요하지 않은 경우 이 기능을 사용할 수 없음).  <br/> | 다음 시간(분) 후에 액세스 요구 사항 다시 확인  <br/>  다음도 설정합니다.  <br/> **시간 제한** 이 분으로 설정됨  <br/>  Microsoft 365 Business에서 설정한 시간(분)과 동일합니다.  <br/> **오프라인 유예 기간** 이 기본적으로 720분으로 설정됨  <br/> |
|탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부  <br/> |무단 해제되거나 루팅된 장치에서 관리되는 앱이 실행되지 않도록 차단  <br/> |
|사용자가 Office 앱의 콘텐츠를 개인 앱으로 복사할 수 있도록 허용  <br/> | 다른 앱에서 잘라내기, 복사 및 붙여넣기 제한  <br/>  Microsoft 365 Business Premium 옵션을 으로 설정하면 다음 세 가지 옵션도 Intune의 **모든 앱으로** 설정됩니다.  <br/> **앱에서 다른 앱으로 데이터를 전송할 수 있도록 허용** <br/> **앱에서 다른 앱의 데이터를 받을 수 있도록 허용** <br/> **다른 앱에서 잘라내기, 복사 및 붙여넣기 제한** <br/>  Microsoft 365 Business 옵션을 **On**(켜기)으로 설정하는 경우 모든 Intune 옵션이 다음과 같이 설정됩니다.  <br/> **앱에서 다른 앱으로 데이터를 전송할 수 있도록 허용** 이 **정책 관리 앱** 으로 설정됨 <br/> **앱에서 다른 앱의 데이터를 받을 수 있도록 허용** 이 **모든 앱** 으로 설정됨 <br/> **다른 앱에서 잘라내기, 복사 및 붙여넣기 제한** 이 **Policy Managed apps with Paste-In**(붙여넣기에 정책 관리된 앱)으로 설정됨 <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 앱 보호 설정

다음 표에서는 Windows 10 응용 프로그램 정책 설정을 Intune 설정에 매핑하는 방법을 보여 줍니다.
  
Intune 설정을 찾으면 Microsoft 365 Business Premium 관리자 자격 증명으로 로그인하고 [Azure Portal로 이동하세요.](https://portal.azure.com) 추가 **서비스를 선택하고** 필터 에 Intune을 **입력합니다.** **Intune 앱 보호 앱** \> **정책을 선택합니다.**
  
 > [!IMPORTANT]
 >
 >Microsoft 365 Business Premium 구독을 사용하면 해당 구독에서 사용할 수 있는 설정에 매핑되는 Intune 설정만 수정할 수 Microsoft 365 Business Premium. 
  
사용 가능한 설정을 탐색하려면 원하는 정책 이름을 선택한 다음 왼쪽 탐색 창에서 **일반, 할당,** 허용된  **앱,** 제외 **앱,** **필수** 설정 또는 고급 설정을 선택합니다. 
  
|**Windows 10 응용 프로그램 정책 설정**|**Intune 설정**|
|:-----|:-----|
|작업 파일 암호화  <br/> |**고급 설정** \> **데이터 보호**: **등록 취소 시 암호화 키 취소** 및 **Revoke access to protected data device enrolls to MDM**(MDM에 보호된 데이터 장치 등록에 대한 액세스 취소)이 모두 **On**(켜기)으로 설정됩니다.  <br/> |
|사용자가 회사 데이터를 개인 파일에 복사하지 못하게 합니다.  <br/> |**필수 설정** \> **Windows Information Protection 모드**. **On** in Microsoft 365 Business Premium maps to: **Hide Overrides** **,** off in Microsoft 365 Business Premium maps to: **Off.**  <br/> |
|Office 문서 액세스 제어  <br/> | 이 설정이 에서 **On으로** Microsoft 365 Business Premium  <br/> 다음 추가 설정과 함께 **고급 설정** \> **액세스**, **Windows에 로그인하는 방법으로 비즈니스용 Windows Hello를 사용합니다.** 가 **On**(켜기)으로 설정됩니다.    <br/> **PIN에 대해 필요한 최소 문자 수를 설정합니다.** 가 **4** 로 설정됩니다.    <br/> **비즈니스용 Windows Hello PIN에 대문자 사용을 구성합니다.** 가 **Do not allow use of upper case letters for PIN**(PIN에 대문자 사용 허용 안 함)으로 설정됩니다.    <br/> **비즈니스용 Windows Hello PIN에 소문자 사용을 구성합니다.** 가 **Do not allow use of upper case letters for PIN**(PIN에 소문자 사용 허용 안 함)으로 설정됩니다.    <br/> **비즈니스용 Windows Hello PIN에 특수 문자 사용을 구성합니다.** 가 **PIN에 특수 문자 사용 허용 안 함** 으로 설정됩니다.    <br/> **시스템에서 사용자가 변경을** 요구하기 전에 PIN을 사용할 수 있는 기간(일)을 **0으로 지정합니다.**  <br/> **다시 사용할 수 없는 사용자 계정에 연결할 수 있는 이전 PIN의 숫자를 지정합니다.** 가 **0** 으로 설정됩니다.    <br/> **장치가 초기화되기 전 허용되는 인증 실패 횟수** 가 Microsoft 365 Business의 설정과 동일하게 설정됩니다(기본적으로 5).  <br/> **장치가 유휴 상태로 전환된 후 장치의 PIN 또는 암호가 잠기게 되는 최대 허용 시간(분)** 이 Microsoft 365 Business의 설정과 동일하게 설정됩니다.  <br/> |
|보호된 데이터의 복구 사용  <br/> |**고급 설정** \> **데이터 보호**: **엔터프라이즈 데이터 보호 아이콘 표시** 및 **WIP에 대해 Azure RMS 사용** 이 **On**(켜기)으로 설정됩니다.  <br/> |
|추가 회사 클라우드 위치 보호  <br/> |**고급 설정** \> **도메인 보호** 및 **클라우드 리소스** 에서 도메인 및 SharePoint 사이트를 표시합니다.  <br/> |
|이러한 앱에서 사용하는 파일이 보호됨  <br/> |보호된 앱 목록이 **허용된 앱** 에 나열됩니다.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 장치 보호 설정

다음 표에서는 Windows 10 장치 구성 설정을 Intune 설정에 매핑하는 방법을 보여 줍니다.
  
Intune 설정을 찾으면 Microsoft 365 Business Premium 관리자 자격 증명으로 로그인하고 Azure [Portal로](https://portal.azure.com)이동한 다음 추가 서비스 를 선택하고 필터에 Intune을 **입력하고** **Intune** 장치 구성 \>  \> **프로필을 선택합니다.** 그런 다음 **Windows 10에 대한 장치 정책** \> **속성** \> **설정** 을 선택합니다.
  
|**Windows 10 장치 정책 설정**|**Intune 설정**|
|:-----|:-----|
|Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원  <br/> |실시간 모니터링 허용 = 켜기  <br/> 클라우드 보호 허용 = 켜기  <br/> 사용자에게 샘플 제출 확인 = 자동으로 안전한 샘플 보내기(기본 비 PII 자동 제출)  <br/> |
|Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원  <br/> |**Edge 브라우저 설정** 의 **SmartScreen** 이 **필수** 로 설정됩니다.  <br/> |
|이 시간 동안 유휴 상태일 때 장치 화면 끄기(분)  <br/> |화면이 잠기기 전까지 최대 비활성 시간(분)  <br/> |
|사용자가 Microsoft Store에서 앱을 다운로드할 수 있도록 허용  <br/> |사용자 지정 URI 정책  <br/> |
|사용자가 Cortana에 액세스할 수 있도록 허용  <br/> |**일반** \> Microsoft 365  Business Premium에서 **Cortana가** 꺼진 경우 Intune에서 차단으로 설정됩니다.   <br/> |
|사용자가 Microsoft에서 Windows 팁 및 광고를 받을 수 있도록 허용  <br/> |**Windows 스포트라이트**, Microsoft 365 Business Premium에서 해제로 설정된 경우 모두 차단됩니다.   <br/> |
|자동으로 Windows 10 장치를 최신 상태로 유지  <br/> | 이 설정은 **Microsoft Intune** 서비스 업데이트 \> **- Windows 10 업데이트 링에서** Windows **10 장치에** 대한 업데이트 정책, 속성 **설정을** \> **선택합니다.**  <br/>  Microsoft 365 Business Premium 설정을 **으로** 설정하면 다음 설정이 모두 설정됩니다.  <br/> **서비스 분기가** **CB(Microsoft** 365 Business Premium에서 꺼져 있는 경우 CBB)로 설정됩니다.  <br/> **Microsoft 제품 업데이트** 는 **허용** 으로 설정됩니다.  <br/> **Windows 드라이버** 는 **허용** 으로 설정됩니다.  <br/> **자동 업데이트 동작** 은 다음 설정과 함께 **유지 관리 시간에 자동 설치** 로 설정됩니다.  <br/> **After hours start**(초과 근무 시간 시작)가 **오전 6시** 로 설정됩니다.  <br/> **활성 시간 끝** 이 **오후 10시** 로 설정됩니다.  <br/> **품질 업데이트 지연 기간(일)** 은 **0** 으로 설정됩니다.  <br/> **기능 업데이트 지연 기간(일)** 은 **0** 으로 설정됩니다.  <br/> **배달 최적화 다운로드 모드** 는 **동일한 NAT 뒤의 피어링과 혼합된 HTTP** 로 설정됩니다.  <br/> |
|||
