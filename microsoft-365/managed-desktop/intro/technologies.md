---
title: Microsoft Managed Desktop 기술
description: 이 문서에서는 Microsoft Managed Desktop에서 사용되는 기술 및 앱을 나열합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840904"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop 기술

이 문서에는 Microsoft Managed Desktop에서 사용되는 기술 및 앱이 나열됩니다.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

모든 Microsoft Managed Desktop 사용자에게는 Microsoft 365 Enterprise 라이선스가 필요합니다. 서비스의 라이선스 요구 사항에 대한 자세한 내용은 [Microsoft Managed Desktop의 사전 요구 사항을 참조하세요.](../get-ready/prerequisites.md)

이 문서에서는 필수 Enterprise 라이선스에 포함된 구성 요소를 요약하고 서비스에서 Microsoft Managed Desktop 장치에서 각 구성 요소를 사용하는 방법에 대한 설명을 제공합니다. 각 영역에 대한 특정 역할 및 책임은 Microsoft Managed Desktop 설명서에서 자세히 설명됩니다. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 또는 E5
 |
 --- | ---
엔터프라이즈용 Microsoft 365 앱(64비트) | 이러한 Office 응용 프로그램은 Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote와 함께 발송됩니다.<br><br>64비트 정식 버전의 Microsoft Project 및 Microsoft Visio는 포함되지 않습니다. 그러나 이러한 응용 프로그램의 설치는 엔터프라이즈용 Microsoft 365 앱 설치에 따라 달라지기 때문에 Microsoft Managed Desktop은 기본 Microsoft Intune 배포 및 보안 그룹을 만들어 라이선스가 있는 사용자에게 이러한 응용 프로그램을 배포하는 데 사용할 수 있습니다. 자세한 내용은 Microsoft Managed Desktop 장치에 Microsoft Project 또는 [Microsoft Visio 설치를 참조하세요.](../get-started/project-visio.md)
OneDrive |Azure Active Directory Single Sign-On은 사용자가 OneDrive에 처음 로그인할 때 사용하도록 설정됩니다.<br><br>"데스크톱", "문서" 및 "그림" 폴더에 대한 알려진 폴더 리디렉션이 포함됩니다. Microsoft Managed Desktop에서 사용하도록 설정하고 구성합니다.
스토어 앱 |    Microsoft Sway 및 Power BI는 디바이스와 함께 배송되지 않습니다. 이러한 앱은 Microsoft Store에서 다운로드할 수 있습니다.
Win32 응용 프로그램 |    Teams는 디바이스와 함께 제공되지 않지만 Microsoft에서 Microsoft Managed Desktop 장치용 패키지 및 제공합니다. Azure Information Protection Client는 디바이스와 함께 제공되지 않지만 배포를 위해 패키지로 만들 수 있습니다.
웹 응용 프로그램 |  Yammer, 브라우저의 Office, Delve, Flow, StaffHub, PowerApps 및 Planner는 디바이스와 함께 배송되지 않습니다. 사용자는 브라우저를 사용하여 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender가 있는 Windows 10 Enterprise E5 또는 E3

 |
 --- | ---
App-V(Application Virtualization) |    고객은 Intune Win32 앱 관리 클라이언트를 사용하여 App-V 패키지를 배포할 수 있습니다.
엔드포인트용 Microsoft Defender |    Microsoft Managed Desktop은 이 제품을 사용하여 장치 보안을 모니터링합니다. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 및 Azure Active Directory Premium P2의 모든 기능을 사용하여 MDM 장치를 관리할 수 있습니다.
Microsoft Cloud App Security |  Microsoft Managed Desktop에서 이 선택적 기능을 사용할 수 있습니다.
Azure Information Protection P2  | Microsoft Managed Desktop에서 이 선택적 기능을 사용할 수 있습니다.
