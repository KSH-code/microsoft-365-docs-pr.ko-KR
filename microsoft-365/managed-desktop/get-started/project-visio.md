---
title: Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio 설치
description: Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio 설치에 대 한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 203db332e1fcd7861f40c69b138ac8274544dceb
ms.sourcegitcommit: 6cabf0226de1c95bff6ddb1852dac5ecdb2d6b96
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "35830476"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio 설치

Microsoft Managed Desktop 장치에 특정 단계를 설치 해야 합니다. 이 항목에서는 이러한 응용 프로그램의 필수 구성 요소 및 설치 프로세스에 대해 설명 합니다.

## <a name="prerequisites"></a>필수 구성 요소

관리자는 다음과 같은 필수 구성 요소를 충족 하는지 확인 해야 합니다.
- **라이선스 수량** -사용자가 올바른 microsoft Project 및 microsoft Visio 라이선스를 사용할 수 있어야 합니다. Microsoft Managed Desktop은 현재 이러한 응용 프로그램의 64 비트 버전만 지원 합니다. 
- **라이선스 이름** -이러한 응용 프로그램에 해당 하는 라이선스 이름은 다음과 같습니다.
    - **Microsoft project** -Project online Professional 또는 Project online Premium
    - **Microsoft visio** -Visio Online 계획 2
- **회사 포털** -사용자가 이러한 응용 프로그램을 설치 하려면 테 넌 트에서 회사 포털을 사용할 수 있어야 합니다. 회사 포털이 테 넌 트에 배포 되어 있지 않으면 [회사 포털](company-portal.md)을 참조 하세요.

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Microsoft Managed Desktop devices 프로젝트 및 Visio 배포
지원 요청을 제출 하면 Microsoft Managed Desktop이 microsoft Intune을 통해 3 개의 Azure AD 그룹 및 세 개의 응용 프로그램 배포를 만들어 테 넌 트에 앱을 배포 합니다.  

**프로젝트 및 Visio를 배포 하려면**
1. **지원 요청 파일** IT 관리자는 이러한 응용 프로그램을 사용자에 게 제공 하기 위해 지원 요청을 파일 해야 합니다. Microsoft Managed Desktop에 연결 하는 방법에 대 한 자세한 내용은 [Microsoft Managed desktop의 관리자 지원을](../working-with-managed-desktop/admin-support.md)참조 하십시오.
2. **새 AZURE AD 그룹에 사용자 할당** Microsoft Managed Desktop은 테 넌 트에 3 개의 Azure AD 그룹을 만들고 해당 응용 프로그램 배포를 3 개 만듭니다. IT 관리자는 사용자를 적절 한 그룹에 할당 해야 합니다.

>[!NOTE]
>사용자를 다음 Azure AD 그룹 중 하나에만 할당 합니다. 

Azure AD 그룹 이름 | 어떤 사용자를 지정 해야 하나요?   
 --- | ---
현대 회사-Office-프로젝트-설치 | 프로젝트만 필요한 사용자
현대 회사-Office-Visio-설치 | Visio만 필요한 사용자
현대적인 작업 공간-Office-프로젝트 및 Visio 설치 | 프로젝트 및 Visio가 필요한 사용자

이러한 그룹에 할당 되 면 회사 포털에서 응용 프로그램을 사용할 수 있습니다. 동기화 하는 데 몇 분 정도 걸릴 수 있지만 사용자가 회사 포털에서 앱을 설치할 수 있습니다. 

## <a name="communicate-changes"></a>변경 내용 전달
IT 관리자는 사용자에 게 프로젝트 및 Visio 설치 방법을 알려 주는 것이 중요 합니다. 성능 저하를 줄여주는 방법에는 다음이 포함됩니다. 
- 사용자에 게 이러한 응용 프로그램을 사용할 수 있는 시기를 알립니다. 
- 회사 포털에서 이러한 응용 프로그램을 설치 하는 방법에 대 한 지침입니다.

>[!NOTE]
>사용자는 회사 포털에서 Microsoft Project 또는 Microsoft Visio를 설치 하기 전에 모든 Office 응용 프로그램을 닫아야 합니다. 
