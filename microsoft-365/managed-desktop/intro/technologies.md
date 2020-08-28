---
title: Microsoft Managed Desktop 기술
description: 이 항목에서는 Microsoft Managed Desktop에 사용 되는 기술과 앱을 소개 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4af346877b41b03c07750508ff93661cc642ec4
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289108"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop 기술

이 항목에서는 Microsoft Managed Desktop에 사용 되는 기술과 앱을 소개 합니다.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise 라이선스는 모든 Microsoft 관리 되는 데스크톱 사용자에 게 필요 합니다. 서비스에 대 한 라이선스 요구 사항에 대 한 자세한 내용은 [Microsoft Managed Desktop의 필수 구성 요소](../get-ready/prerequisites.md)를 참조 하세요.

이 항목에서는 필요한 엔터프라이즈 라이선스에 포함 된 구성 요소에 대해 설명 하 고, 서비스가 Microsoft Managed Desktop 장치에서 각 구성 요소를 사용 하는 방법에 대 한 설명을 제공 합니다. 각 영역에 대 한 특정 역할과 책임은 Microsoft Managed Desktop 설명서 전반에 자세히 설명 되어 있습니다. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 또는 E5
 |
 --- | ---
Microsoft 365 Apps for enterprise (64 비트) | 이러한 Office 응용 프로그램은 Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote와 함께 제공 됩니다.<br><br>64 비트 정식 버전의 Microsoft Project 및 Microsoft Visio는 포함 되지 않습니다. 그러나 이러한 응용 프로그램의 설치는 Microsoft 365 Apps for enterprise 설치에 따라 달라 지기 때문에, Microsoft Managed Desktop은 기본 Microsoft Intune 배포 및 보안 그룹을 만든 다음이를 사용 하 여 라이선스 사용자에 게 이러한 응용 프로그램을 배포할 수 있습니다. 자세한 내용은 microsoft [Managed 데스크톱 장치에서 Microsoft Project 또는 Microsoft Visio 설치](../get-started/project-visio.md)를 참조 하세요.
비즈니스용 OneDrive |Azure Active Directory Single Sign-on은 사용자가 비즈니스용 OneDrive에 처음 로그인 할 때 사용 하도록 설정 됩니다.<br><br>"Desktop", "Document" 및 "Pictures" 폴더에 대해 알려진 폴더 리디렉션이 포함 됩니다. Microsoft Managed Desktop에서 사용 하도록 설정 하 고 구성 합니다. 
스토어 앱 |    Microsoft Sway 및 Power BI는 장치와 함께 제공 되지 않습니다. 이러한 앱은 Microsoft Store에서 다운로드할 수 있습니다.
Win32 응용 프로그램 |    팀은 장치와 함께 제공 되지 않지만 microsoft에서 관리 되는 데스크톱 장치용으로 패키지화 되 고 제공 됩니다. Azure Information Protection 클라이언트는 장치와 함께 제공 되지 않지만이 패키지를 배포용으로 사용할 수 있습니다. 
웹 응용 프로그램 |  Yammer, Office for browser, Delve, 흐름, StaffHub, PowerApps 및 Planner가 장치와 함께 제공 되지 않습니다. 사용자는 브라우저를 사용 하 여 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 Enterprise E3 또는 E5

 |
 --- | ---
Application Virtualization (App-v) |    고객은 Intune Win32 앱 관리 클라이언트를 사용 하 여 App-v 패키지를 배포할 수 있습니다.
Microsoft Defender Advanced Threat Protection |  Microsoft Managed Desktop은이를 사용 하 여 장치 보안을 모니터링 합니다. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 및 Azure Active Directory Premium P2의 모든 기능을 사용 하 여 MDM 장치를 관리할 수 있습니다.
Microsoft Cloud App Security |  이 선택적 기능은 Microsoft Managed Desktop에서 사용할 수 있습니다.
Azure Information Protection P2  | 이 선택적 기능은 Microsoft Managed Desktop에서 사용할 수 있습니다.
