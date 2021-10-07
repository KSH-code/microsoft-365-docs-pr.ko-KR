---
title: Microsoft Project 장치에 Visio 또는 Microsoft Microsoft Managed Desktop 설치
description: Microsoft Project 또는 Microsoft Visio 설치에 대한 Microsoft Managed Desktop 정보
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: af5470d0993c54c1593526a7e0e3ae0b6e239065
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199792"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Project 장치에 Visio 또는 Microsoft Microsoft Managed Desktop 설치

Microsoft Project Microsoft Visio 디바이스에 특정 단계를 설치해야 Microsoft Managed Desktop 합니다. 이 항목에서는 이러한 응용 프로그램의 선행 구성 및 설치 프로세스를 문서화합니다.

## <a name="prerequisites"></a>필수 구성 요소

관리자는 다음 선행 요구 사항을 충족하는지 확인해야 합니다.
- **라이선스 수량** - 사용자에게 올바른 Microsoft Project Microsoft Visio 라이선스를 사용할 수 있어야 합니다. Microsoft Managed Desktop 현재 이러한 응용 프로그램의 64비트 버전만 지원합니다. 
- **라이선스 이름** - 이러한 응용 프로그램에 적합한 라이선스 이름은:
    - **Microsoft Project** - Project Online Professional 또는 Project Online Premium
    - **Microsoft Visio** - Visio Online 계획 2
- **회사 포털** - 회사 포털 응용 프로그램을 설치하려면 테넌트에서 이 응용 프로그램을 사용할 수 있어야 합니다. 테넌트에 회사 포털 배포되지 않은 경우 [회사 포털.](company-portal.md)

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>장치용 Project Visio 및 Microsoft Managed Desktop 배포
Microsoft Managed Desktop Microsoft Project Microsoft Visio 두 개의 Win32 응용 프로그램으로 Microsoft Intune. 또한 "사용 가능한" 의도를 Azure Active Directory 응용 프로그램에 할당되는 두 개의 그룹도 만들 것입니다. 

**배포 Project Visio** 해당 그룹에 사용자를 추가하면 응용 프로그램을 해당 그룹에서 사용할 수 회사 포털. 동기화하는 데 몇 분 정도 걸릴 수 있지만 사용자가 앱의 앱을 설치할 수 회사 포털. 

Azure AD 그룹 이름 | 할당할 사용자   
 --- | ---
최신 Workplace-Office-Project_Install | 사용자가 필요한 Project
최신 Workplace-Office-Visio_Install | 사용자가 필요한 Visio

## <a name="communicate-changes"></a>변경 내용 전달
IT 관리자는 IT 관리자에게 설치 방법과 설치 방법을 Project Visio. 여기에는 다음이 포함됩니다. 
- 이러한 응용 프로그램을 사용할 수 있는 경우 사용자에게 알릴 수 있습니다. 
- 설치 프로그램에서 이러한 응용 프로그램을 설치하는 방법에 대한 회사 포털.
