---
title: Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio 설치
description: Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio를 설치하는 방법 정보
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950535"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio 설치

Microsoft Project 및 Microsoft Visio를 사용하려면 Microsoft Managed Desktop 장치에 특정 단계를 설치해야 합니다. 이 항목에서는 이러한 응용 프로그램의 선행 구성 및 설치 프로세스를 문서화합니다.

## <a name="prerequisites"></a>필수 구성 요소

관리자는 다음 선행 요구 사항을 충족하는지 확인해야 합니다.
- **라이선스 수량** - 사용자가 올바른 양의 Microsoft Project 및 Microsoft Visio 라이선스를 사용할 수 있어야 합니다. Microsoft Managed Desktop은 현재 이러한 응용 프로그램의 64비트 버전만 지원합니다. 
- **라이선스 이름** - 이러한 응용 프로그램에 적합한 라이선스 이름은 다음입니다.
    - **Microsoft Project** - Project Online Professional 또는 Project Online Premium
    - **Microsoft Visio** - Visio Online 계획 2
- **회사 포털** - 사용자가 이러한 응용 프로그램을 설치하려면 테넌트에서 회사 포털을 사용할 수 있어야 합니다. 회사 포털이 테넌트에 배포되지 않은 경우 회사 [포털을 참조합니다.](company-portal.md)

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Microsoft Managed Desktop 장치용 Project 및 Visio 배포
Microsoft Managed Desktop은 Microsoft Intune에서 Microsoft Project 및 Microsoft Visio를 두 개의 Win32 응용 프로그램으로 추가합니다. 또한 Azure Active Directory에서 "사용 가능한" 의도를 사용하여 해당 응용 프로그램에 할당되는 두 개의 그룹을 만들 것입니다. 

**Project 및 Visio를 배포하는 경우** 해당 그룹에 사용자를 추가하면 회사 포털에서 응용 프로그램을 사용할 수 있습니다. 동기화하는 데 몇 분 정도 걸릴 수 있지만 사용자는 회사 포털에서 앱을 설치할 수 있습니다. 

Azure AD 그룹 이름 | 할당할 사용자   
 --- | ---
최신 Workplace-Office-Project_Install | Project가 필요한 사용자
최신 Workplace-Office-Visio_Install | Visio가 필요한 사용자

## <a name="communicate-changes"></a>변경 내용 전달
IT 관리자는 사용자에게 Project 및 Visio 설치 방법을 알려야 합니다. 여기에는 다음이 포함됩니다. 
- 이러한 응용 프로그램을 사용할 수 있는 경우 사용자에게 알릴 수 있습니다. 
- 회사 포털에서 이러한 응용 프로그램을 설치하는 방법에 대한 지침입니다.
