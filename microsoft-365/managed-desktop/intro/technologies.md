---
title: 데스크톱을 관리 하는 Microsoft 기술
description: 이 항목의 기술와 Microsoft 관리 되는 데스크톱에 사용 되는 응용 프로그램을 나열 합니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: da0268c6b0eddbd44cf62de2a95b963a443c3278
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869924"
---
# <a name="microsoft-managed-desktop-technologies"></a>데스크톱을 관리 하는 Microsoft 기술

이 항목의 기술와 Microsoft 관리 되는 데스크톱에 사용 되는 응용 프로그램을 나열 합니다.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 e 5 라이선스 (또는에 상응)은 데스크톱을 관리 하는 Microsoft 서비스에 필요 합니다. 이 라이선스 및 데스크톱을 관리 하는 Microsoft 데스크톱을 관리 하는 Microsoft 장치와 각 구성 요소를 사용 하는 방법에 포함 된 모든 구성 요소는 다음과 같습니다.  특정 역할 및 책임 각 영역에 대 한 전체 데스크톱을 관리 하는 Microsoft 항목에서 자세히 설명 합니다. 

Microsoft 365 e 5는 3 구성 요소로 이루어져: Office 365 e 5 "," Windows 10 Enterprise "및" e 5 "," Enterprise 이동성 "+" 보안 e 5입니다.  

## <a name="office-365-e5"></a>Office 365 e 5
 |
 --- | ---
Office 365 표준 제품군 (64 비트) * | 응용 프로그램의 표준 Office 제품군 장치 함께 제공 됩니다: Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스, OneNote에 대 한 Skype 합니다.<br><br>64 비트 하 고 실행을 클릭 (C2R) 전체 버전의 Microsoft Project 및 Microsoft Visio는 Office 365 표준 제품군에 포함 되지 않습니다.  그러나 이러한 응용 프로그램의 설치 되는 표준 Office 제품군 설치에 따라 다릅니다, 이후 데스크톱을 관리 하는 Microsoft가 만든 기본 Intune 배포 하 고 이러한 응용 프로그램을 배포 하는 고객에서 사용할 보안 그룹 최종 사용자에 게 사용이 허가 됩니다.  
앱을 저장 합니다. |    Microsoft 영향, Microsoft 팀의, Power BI 데스크톱 (하지 Pro)에 포함 되지 않은 장치입니다. 이러한 응용 프로그램은 Microsoft 저장소에서 다운로드할 수 있습니다.
Win32 응용 프로그램 |    Power BI Pro, Azure 정보를 보호 하는 클라이언트 및 Microsoft 플래너 장치와 함께 제공 하지 않는 및 고객에 의해 배포에 대 한 패키지화 할 수 있습니다. 
웹 응용 프로그램 |  Yammer, Delve, Office Online, 흐름, StaffHub, PowerApps 장치와 함께 제공 되지 않습니다. 사용자가 브라우저를 통해 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.
비즈니스 온라인 클라우드 PBX에 대 한 Skype | 이 기능은 Office 365 e 5를 통해 사용할 수 있습니다. 데스크톱을 관리 하는 Microsoft에서이 서비스의 모든 측면을 구성 하지 않습니다.

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise e 5

 |
 --- | ---
자격 증명 Guard |  데스크톱을 관리 하는 Microsoft가 지침을 제공 하 고이 기능의 클라우드 측면을 관리
장치 Guard (Windows Defender 응용 프로그램 제어)   | Microsoft 관리 되는 데스크톱 정책이 만들어집니다. 고객 서명 관리
AppLocker 관리 |  Microsoft 관리 되는 데스크톱 정책이 만들어집니다. 고객 서명 관리
응용 프로그램 가상화 (App-v) |    Microsoft 관리 되는 데스크톱 Intune에서 지원 되지 않습니다으로이 유형의 배포를 지원 하지 않습니다.
사용자 환경 가상화 (사용자 교육-V) | 이 Microsoft에 관리 하는 바탕 화면을 관리 하는 장치는 사용 되지 않습니다.
관리 되는 사용자 환경  | 이 값은 Microsoft에 관리 하는 바탕 화면을 관리 하는 장치는 사용 되지 않습니다. MDM 장치 관리에 대 한 솔루션으로 사용 됩니다.
Windows Defender Advanced Threat Protection |   이 장치 보안 정책을 관리 하려면 Microsoft 관리 되는 데스크톱에서 사용 됩니다. 

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security 

 |
 --- | ---
엔터프라이즈 이동성 + 보안 E3<br>Azure Active Directory 프리미엄 P2 |    MDM 장치를 관리 하는 엔터프라이즈 이동성 + 보안 E3 및 AADP의 모든 측면을 사용할 수 있습니다.
Microsoft Cloud App Security |  이것은 고객이 Microsoft 관리 되는 데스크톱 서비스와 함께 사용할 수 있는 선택적 기능입니다.
Azure 정보 보호 P2  |이것은 고객이 Microsoft 관리 되는 데스크톱 서비스와 함께 사용할 수 있는 선택적 기능입니다.