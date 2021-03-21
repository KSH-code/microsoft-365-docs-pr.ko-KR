---
title: 장치에 Intune 회사 포털 설치
description: Microsoft Managed Desktop 디바이스에 회사 포털 앱 설치에 대한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 회사 포털
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925777"
---
# <a name="install-intune-company-portal-on-devices"></a>장치에 Intune 회사 포털 설치

Microsoft Managed Desktop을 사용하려면 IT 관리자가 Microsoft Managed Desktop 장치를 사용하여 사용자를 위해 Intune 회사 포털을 설치해야 합니다. 다음은 조직에 대한 몇 가지 이점입니다.
- 사용자는 사용 가능한 응용 프로그램을 찾아서 설치할 수 있는 한 곳이 있습니다. 
- IT 관리자는 사용자에 대한 범주별로 응용 프로그램을 구성할 수 있습니다.  
- 일부 응용 프로그램(예: Microsoft Project 및 Microsoft Visio)에서는 회사 포털이 Microsoft Managed Desktop과 함께 배포해야 합니다.
- IT 관리자는 조직에 맞게 회사 포털을 사용자 지정할 수 있습니다. 여기에는 브랜드 이미징, 로컬 지원 연락처 추가 등이 포함됩니다. 자세한 내용은 Microsoft Intune 회사 포털 앱을 구성하는 [방법을 참조하세요.](/intune/company-portal-app)   

이 항목에서는 Microsoft Managed Desktop 사용자에게 Intune 회사 포털을 배포하는 프로세스를 문서화합니다. 전체 프로세스는 다음과 같습니다.
1. 비즈니스용 Microsoft Store에서 회사 포털 구매 및 Intune과 동기화
2. 사용자에게 회사 포털 할당
3. 사용자에게 변경 내용을 전달합니다.

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>1단계 - 비즈니스용 Microsoft Store에서 회사 포털 구매 및 Intune과 동기화
앱을 구매하고 Intune과 동기화하는 방법에 대한 자세한 내용은 *Deploy apps to Microsoft Managed Desktop devices에서* 비즈니스용 Microsoft [Store](deploy-apps.md#msfb-apps) 앱을 참조하세요.

이 항목에서는 다음 방법에 대한 정보를 제공합니다. 
- 비즈니스용 Microsoft Store에서 회사 포털 구매 
- Intune과 비즈니스용 Microsoft Store 간의 강제 동기화
- Intune과 비즈니스용 Microsoft Store 간의 활성 동기화 확인 

## <a name="step-2---assign-company-portal-to-your-users"></a>2단계 - 사용자에게 회사 포털 할당
Microsoft Managed Desktop에 등록한 후 Microsoft Managed Desktop Operations는 자동으로 테넌트에 회사 포털을 배포하고 조직의 Microsoft Managed Desktop 장치에 앱을 설치합니다.

## <a name="step-3---communicate-change-to-your-users"></a>3단계 - 사용자에게 변경 내용을 전달
조직의 IT 관리자는 조직에서 회사 포털을 사용하는 방법을 사용자에게 알려야 합니다. Microsoft Managed Desktop에서 권장되는 권장 사항:
- 회사 포털에서 응용 프로그램을 설치하는 단계입니다. 자세한 내용은 장치에 앱 설치 및 [공유를 참조하세요.](/intune-user-help/install-apps-cpapp-windows)
- 현재 사용할 수 없는 응용 프로그램에 대한 요청을 IT 관리자에게 보내는 방법 자세한 내용은 [Request an app for work or school을 참조하세요.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털에서 관리자 연락처 추가 및 확인](add-admin-contacts.md)
2. [조건부 액세스 조정](conditional-access.md)
3. [라이선스 할당](assign-licenses.md)
4. Intune 회사 포털 배포(이 항목)
5. [엔터프라이즈 상태 로밍 사용](enterprise-state-roaming.md)
6. [장치 설정](set-up-devices.md)
7. [사용자들이 장치를 사용할 수 있도록 준비시키기](get-started-devices.md)
8. [앱 배포](deploy-apps.md)