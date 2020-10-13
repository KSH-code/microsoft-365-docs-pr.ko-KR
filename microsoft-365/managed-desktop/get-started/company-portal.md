---
title: 장치에 Intune 회사 포털 설치
description: Microsoft Managed Desktop 장치에 회사 포털 앱을 설치 하는 방법에 대 한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 회사 포털
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d457c4b96e47485eee041b72a1cf24e96a13bf18
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430190"
---
# <a name="install-intune-company-portal-on-devices"></a>장치에 Intune 회사 포털 설치

Microsoft Managed Desktop을 사용 하려면 IT 관리자가 Microsoft Managed Desktop devices 사용자를 위해 Intune 회사 포털을 설치 해야 합니다. 조직의 몇 가지 이점은 다음과 같습니다.
- 사용자는 사용 가능한 응용 프로그램을 찾아보고 설치 하기 위한 한 가지 장소를가지고 있습니다. 
- IT 관리자는 사용자를 위해 범주별로 응용 프로그램을 구성할 수 있습니다.  
- Microsoft Project 및 Microsoft Visio와 같은 일부 응용 프로그램의 경우에는 회사 포털이 Microsoft Managed Desktop을 사용 하 여 배포 해야 합니다.
- IT 관리자는 조직의 회사 포털을 사용자 지정할 수 있습니다. 여기에는 브랜드 이미징, 로컬 지원 연락처에 추가 등이 포함 됩니다. 자세한 내용은 [How To Configure The Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app)를 참조 하세요.   

이 항목에서는 Microsoft Managed Desktop 사용자에 게 Intune 회사 포털을 배포 하는 프로세스에 대해 설명 합니다. 전체 프로세스는 다음과 같습니다.
1. 비즈니스를 위해 Microsoft Store에서 회사 포털 구매 및 Intune과 동기화
2. 사용자에 게 회사 포털 할당
3. 사용자에 게 변경 내용 전달

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>1 단계-비즈니스를 위해 Microsoft Store에서 회사 포털 구매 및 Intune과 동기화
앱을 구입 하 고 Intune과 동기화 하는 방법에 대 한 자세한 내용은 microsoft *Managed 데스크톱 장치에 앱 배포*의 [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) 를 참조 하세요.

이 항목에서는 다음 방법에 대 한 정보를 제공 합니다. 
- 비즈니스를 위해 Microsoft Store에서 회사 포털 구매 
- Intune과 Microsoft Store for Business 간 강제 동기화
- Intune과 Microsoft Store for Business 간의 활성 동기화 확인 

## <a name="step-2---assign-company-portal-to-your-users"></a>2 단계-사용자에 게 회사 포털 할당
Microsoft Managed Desktop Admin 포털을 통해 Microsoft Managed Desktop 작업에 대 한 지원 요청을 제출 합니다. 지원 요청에서 회사 포털에 사용자를 할당 하도록 요청 합니다. Microsoft Managed Desktop은 회사 포털을 테 넌 트에 배포 하 고 조직의 Microsoft Managed Desktop 장치에 앱을 설치 합니다.

Microsoft Managed Desktop에서 지원 요청을 제출 하는 방법에 대 한 자세한 내용은 [Microsoft Managed desktop에 대 한 관리자 지원을](../working-with-managed-desktop/admin-support.md)참조 하십시오.

## <a name="step-3---communicate-change-to-your-users"></a>3 단계-사용자에 게 변경 내용 전달
조직의 IT 관리자로 서 사용자에 게 조직에서 회사 포털을 사용 하는 방법을 알려 주는 것이 중요 합니다. Microsoft Managed Desktop이 권장 됩니다.
- 회사 포털에서 응용 프로그램을 설치 하는 단계 자세한 내용은 [장치에 앱 설치 및 공유](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)를 참조 하세요.
- 현재 사용할 수 없는 응용 프로그램에 대 한 요청을 IT 관리자에 게 보내는 방법 자세한 내용은 [회사 또는 학교에 대 한 앱 요청](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)을 참조 하세요.  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털에서 관리자 연락처 추가 및 확인](add-admin-contacts.md)
2. [조건부 액세스 조정](conditional-access.md)
3. [라이선스 할당](assign-licenses.md)
4. Intune 회사 포털 배포 (이 항목)
5. [엔터프라이즈 상태 로밍 사용](enterprise-state-roaming.md)
6. [장치 설정](set-up-devices.md)
7. [사용자들이 장치를 사용할 수 있도록 준비시키기](get-started-devices.md)
8. [앱 배포](deploy-apps.md)
