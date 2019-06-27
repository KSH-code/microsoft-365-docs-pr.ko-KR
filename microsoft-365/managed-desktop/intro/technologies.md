---
title: Microsoft Managed Desktop 기술
description: 이 항목에서는 Microsoft Managed Desktop에 사용 되는 기술과 앱을 소개 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9c0e6481d0dc80e7cf03de2b748935c2f59f132a
ms.sourcegitcommit: e54ec86310a18101f4688890cd5a9fc16bbe6f55
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2019
ms.locfileid: "35257821"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop 기술

이 항목에서는 Microsoft Managed Desktop에 사용 되는 기술과 앱을 소개 합니다.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise 라이선스는 모든 Microsoft 관리 되는 데스크톱 사용자에 게 필요 합니다. 서비스에 대 한 라이선스 요구 사항에 대 한 자세한 내용은 [Microsoft Managed Desktop의 필수 구성 요소](../get-ready/prerequisites.md)를 참조 하세요.

다음은 필요한 엔터프라이즈 라이선스에 포함 된 모든 구성 요소와 서비스가 Microsoft Managed Desktop 장치에서 각 구성 요소를 사용 하는 방법입니다. 각 영역에 대 한 특정 역할과 책임은 Microsoft Managed Desktop 항목 전체에 자세히 나와 있습니다. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64 비트) * | 표준 Office 응용 프로그램 제품군은 Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote와 함께 제공 됩니다.<br><br>C2R (64 비트)를 클릭 하 여 실행 (전체 버전의 Microsoft Project) 및 Microsoft Visio는 Office 365 Standard Suite에 포함 되어 있지 않습니다.  그러나 이러한 응용 프로그램의 설치가 표준 Office 제품군 설치에 종속 되기 때문에 Microsoft Managed Desktop은 고객이 이러한 응용 프로그램을 배포 하는 데 사용할 기본 Intune 배포 및 보안 그룹을 만들었습니다. 최종 사용자 사용권  
스토어 앱 |    Microsoft Sway, Power BI Desktop은 디바이스와 함께 제공 되지 않습니다. 이러한 앱은 Microsoft Store에서 다운로드할 수 있습니다.
Win32 응용 프로그램 |    Power BI Pro, Azure Information Protection 클라이언트 및 Microsoft Planner는 장치와 함께 제공 되지 않으며, 고객의 배포용으로 패키지할 수 있습니다. 
웹 응용 프로그램 |  Yammer, Office Online, Delve, 흐름, StaffHub, PowerApps는 장치와 함께 제공 되지 않습니다. 사용자는 브라우저를 사용 하 여 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.
비즈니스용 Skype Online 클라우드 PBX | 이 기능은 Office 365을 통해 사용할 수 있습니다. Microsoft Managed Desktop은이 서비스의 모든 측면을 구성 하지 않습니다.

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Credential Guard |  Microsoft는이 기능에 대 한 지침을 제공 하 고 클라우드를 관리 합니다.
Application Virtualization (App-v) |    Microsoft Managed Desktop은 Intune에서 지원 되지 않으므로이 유형의 배포를 지원 하지 않습니다.
UE-V (User Experience Virtualization) | 이 기능은 Microsoft Managed Desktop managed 장치에서 사용 되지 않습니다.
관리 되는 사용자 환경  | 이 기능은 Microsoft Managed Desktop managed 장치에서 사용 되지 않습니다. MDM은 장치 관리를 위한 솔루션으로 사용 됩니다.
Windows Defender Advanced Threat Protection |   이는 Microsoft Managed Desktop에서 장치 보안 정책을 관리 하는 데 사용 됩니다. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    엔터프라이즈 이동성 + Security E3 및 AADP의 모든 측면은 MDM 장치를 관리 하는 데 사용 될 수 있습니다.
Microsoft Cloud App Security |  이 기능은 고객이 Microsoft Managed Desktop service에 사용할 수 있는 선택적 기능입니다.
Azure Information Protection P2  |이 기능은 고객이 Microsoft Managed Desktop service에 사용할 수 있는 선택적 기능입니다.
