---
title: 장치에 Intune 회사 포털 설치
description: 디바이스에서 회사 포털 앱을 설치하는 Microsoft Managed Desktop 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 회사 포털
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 57f4d05089a023b5f64f0e27a8e0a20305a02a06
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208724"
---
# <a name="install-intune-company-portal-on-devices"></a>장치에 Intune 회사 포털 설치

Microsoft Managed Desktop 장치를 사용하려면 IT Intune 회사 포털 장치를 설치해야 Microsoft Managed Desktop 합니다. 다음은 조직에 대한 몇 가지 이점입니다.
- 사용자는 사용 가능한 응용 프로그램을 찾아서 설치할 수 있는 한 곳이 있습니다. 
- IT 관리자는 사용자에 대한 범주별로 응용 프로그램을 구성할 수 있습니다.  
- 일부 응용 프로그램(예: Microsoft Project 및 Microsoft Visio)에서는 회사 포털 배포해야 Microsoft Managed Desktop.
- IT 관리자는 조직에 대한 회사 포털 사용자 지정할 수 있습니다. 여기에는 브랜드 이미징, 로컬 지원 연락처 추가 등이 포함됩니다. 자세한 내용은 앱 구성 방법 [을 Microsoft Intune 회사 포털 참조하세요.](/intune/company-portal-app)   

이 항목에서는 사용자 Intune 회사 포털 배포하는 Microsoft Managed Desktop 문서화합니다. 전체 프로세스는 다음과 같습니다.
1. Intune에서 회사 포털 비즈니스용 Microsoft Store 구매 및 동기화
2. 사용자에게 회사 포털 할당
3. 사용자에게 변경 내용을 전달합니다.

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>1단계 - Intune에서 회사 포털 구매 및 비즈니스용 Microsoft Store 동기화
앱을 구매하고 Intune과 동기화하는 방법에 대한 자세한 내용은 deploy apps to [비즈니스용 Microsoft Store apps](deploy-apps.md#msfb-apps) to *Microsoft Managed Desktop 참조하세요.*

이 항목에서는 다음 방법에 대한 정보를 제공합니다. 
- 2016년 회사 포털 구매 비즈니스용 Microsoft Store 
- Intune과 Intune 간의 강제 동기화 비즈니스용 Microsoft Store
- Intune과 Intune 간의 활성 동기화 비즈니스용 Microsoft Store 

## <a name="step-2---assign-company-portal-to-your-users"></a>2단계 - 사용자에게 회사 포털 할당
Microsoft Managed Desktop 등록한 후 테넌트에 회사 포털 자동으로 배포하고 조직의 Microsoft Managed Desktop 장치에 앱을 설치합니다.

## <a name="step-3---communicate-change-to-your-users"></a>3단계 - 사용자에게 변경 내용을 전달
조직의 IT 관리자는 조직에서 사용자들이 조직에서 사용하는 방법을 사용자에게 회사 포털 중요합니다. Microsoft Managed Desktop 권장 사항:
- 다음 단계에서 응용 프로그램을 설치하는 회사 포털. 자세한 내용은 장치에 앱 설치 및 [공유를 참조하세요.](/intune-user-help/install-apps-cpapp-windows)
- 현재 사용할 수 없는 응용 프로그램에 대한 요청을 IT 관리자에게 보내는 방법 자세한 내용은 [Request an app for work or school을 참조하세요.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털](access-admin-portal.md)에 액세스합니다.
1. [관리 포털의 관리자 연락처를 추가하고 확인합니다](add-admin-contacts.md).
1. [등록 후 설정을 조정합니다](conditional-access.md).
1. 배포 및 Intune 회사 포털 할당합니다(이 문서).
1. [라이선스를 할당합니다](assign-licenses.md).
1. [앱을 배포합니다](deploy-apps.md).
1. [장치 설정](set-up-devices.md)
1. [Autopilot 및 등록 상태 페이지의 첫 실행 환경](esp-first-run.md)을 설정합니다.
1. [사용자 지원 기능을 사용하도록 설정합니다](enable-support.md).
1. [사용자가 디바이스를 사용할 수 있도록 준비합니다](get-started-devices.md).
1. [앱 컨트롤을 시작합니다](get-started-app-control.md).
