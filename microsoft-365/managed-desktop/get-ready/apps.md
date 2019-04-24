---
title: Microsoft Managed Desktop 용 앱 준비
description: ''
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289071"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop 용 앱 준비

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
microsoft 및 microsoft managed desktop 고객은 동일 하 게 중요 하지만 microsoft managed desktop에서 사용 되는 응용 프로그램에 대 한 책임은 서로 다릅니다.

## <a name="microsoft-responsibilities"></a>Microsoft의 책임
**Office 365 앱** Microsoft는 특정 Office 365 앱의 배포, 업데이트 및 지원에 대 한 전체 서비스를 제공 합니다. 모든 사용자는 사용자가 빠르게 생산성을 높일 수 있도록 장치 이미지에 포함 된 응용 프로그램의 기본 집합 (64 비트 버전)을 수신 합니다. Office 365 제품군의 프로젝트 및 Visio 응용 프로그램은 별도로 사용이 허가 됩니다.  Microsoft Managed Desktop은 IT 관리자가 라이선스를 관리 하 고 이러한 응용 프로그램을 조직에 적절 하 게 배포할 수 있도록 하는 배포 그룹을 제공 합니다. microsoft는 microsoft 관리 데스크톱 지원 채널을 통해 이러한 응용 프로그램의 최종 사용자를 지원 합니다.

**기간 업무** (lob) 앱 Microsoft는 IT 관리자에 게 Intune 제품의 일부로 최종 사용자에 게 LOB (기간 업무) 응용 프로그램을 관리 하 고 배포할 수 있는 도구를 제공 합니다. Microsoft는 기간 업무 (lob) [응용 프로그램](#line-of-business-applications) 에 설명 된 것 처럼 응용 프로그램 배포 문제를 지원 합니다. 

**Intune을 사용 하 여 배포** intune은 microsoft Managed Desktop 온 보 딩 중 **비즈니스용 microsoft 스토어** 에 연결 되며,이를 통해 확보 된 앱을 Intune을 통해 배포할 수 있습니다. microsoft는 IT 관리자가 최종 사용자에 게 셀프 서비스 환경을 제공할 수 있도록 microsoft Store의 회사 포털 응용 프로그램도 최종 사용자에 게 배포 합니다.

**앱 관리** Microsoft는 시스템에 영향을 주므로 최신 직장에 적합 하지 않은 제한 된 응용 프로그램을 확인할 수 있습니다. 이러한 응용 프로그램이 식별 되 면 Microsoft에서 고객에 게 알리고 해당 응용 프로그램을 테 넌 트에서 제거 해야 합니다. 

제한 된 앱 동작 및 앱 요구 사항에 대 한 자세한 내용은 [Microsoft Managed Desktop app 요구 사항](../service-description/mmd-app-requirements.md) 를 참조 하세요.

## <a name="customer-responsibilities"></a>고객 책임
Office 365 제품군은 microsoft의 생산성 제공에 핵심 이며, 모든 microsoft 관리 데스크톱 사용자의 microsoft 365 라이선스에 포함 되어 있습니다. microsoft에서 관리 하는 데스크톱 장치에 대 한 Office 응용 프로그램을 배포, 업데이트 및 지 원하는 반면, 고객은 여전히 일부 영역을 담당 하 고 있습니다.
- **라이선스 할당** -고객은 최종 사용자에 게 Office 365에 대 한 적절 한 라이선스를 할당 해야 합니다. 
- **보안 그룹에 사용자 추가** -프로젝트나 Visio가 필요한 사용자를 위해 IT 관리자는 해당 사용자를 적절 한 배포 그룹에 추가 해야 합니다. IT 관리자는 해당 사용자의 최종 기간을 관리 하는 역할도 담당 합니다. 
- **Deploy office 365 Add 애드온** -고객이 필요한 것으로 간주 되는 office 365 제품군에 플러그 인을 배포 하는 일을 담당 합니다. 

기간 업무 (lob) 앱은 각 고객에 대해 고유 하므로 고객은 Microsoft에서 배포 하지 않은 조직 내의 모든 응용 프로그램을 관리 해야 합니다. 성능 저하를 줄여주는 방법에는 다음이 포함됩니다.
- 필요한 앱 및 요구 사항 결정
- 해당 사용자에 게 앱 할당
- 앱 할당 관리를 위한 Azure Active Directory (AD) 그룹 만들기 및 유지 관리 

고객은 LOB 앱을 Intune에 업로드 해야 합니다. 그런 다음 각 수명 주기 동안 이러한 응용 프로그램을 배포, 업데이트 및 제거 하 고 사용자를 위해 이러한 앱에 대 한 지원을 관리 하는 일을 담당 합니다.

## <a name="office-applications"></a>Office 응용 프로그램
microsoft 365 E5 라이선스의 일부로, microsoft가 Office 365 Standard Suite (64 비트)를 배포 합니다. 

자세한 내용은 [Microsoft Managed Desktop 기술](../intro/technologies.md) 를 참조 하세요. <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>기간 업무 (lob) 응용 프로그램
이 표에는 기간 업무 (lob) 응용 프로그램의 각 단계에 대 한 책임이 요약 되어 있습니다. 

응용 프로그램 작업 항목 |    고객    | Microsoft
--- | --- | ---
**온 보 딩 앱** |  |
대상 사용자 그룹에 필요한 응용 프로그램 확인   | ![예](images/checkmark.png)  |
앱 배포를 위한 Azure AD 그룹 만들기 및 관리 | ![예](images/checkmark.png) |   
**앱 패키징** |  |
Intune 배포 표준에 맞게 앱 패키지 |  ![예](images/checkmark.png) |  
Intune에 앱 업로드 | ![예](images/checkmark.png)     |
Microsoft Managed Desktop 환경의 앱 테스트 |    ![예](images/checkmark.png) |  
최종 사용자가 포함 된 앱 테스트    | ![예](images/checkmark.png) |    
**배포** | |
사용자 관리 및 응용 프로그램에 할당  | ![예](images/checkmark.png)  |
Intune 배포 도구를 통해 원격 클라이언트에 응용 프로그램 제공| |   ![예](images/checkmark.png)
Intune을 통해 응용 프로그램 업데이트 식별 및 배포 | ![예](images/checkmark.png)    |
중지 된 응용 프로그램을 Unistall 및 제거 합니다.    | ![예](images/checkmark.png) |    
**관리** | |
라이선스 조달 및 할당 |   ![예](images/checkmark.png)     |
기간 업무 (lob) 앱에 대 한 최종 사용자 지원 제공  | ![예](images/checkmark.png) |
원격으로 앱 설정 관리    | ![예](images/checkmark.png) |

LOB 응용 프로그램 요구 사항에 대 한 자세한 내용은 [Microsoft Managed Desktop application 요구 사항](../service-description/mmd-app-requirements.md) 를 참조 하세요.


## <a name="intune-application-deployment"></a>Intune 응용 프로그램 배포
응용 프로그램 관리는 Microsoft Managed Desktop Admin 포털을 통해 또는 Intune 포털을 통해 처리할 수 있습니다. Intune의 앱 관리 포털에는 Windows, Android 및 iOS 용으로 배포 된 응용 프로그램이 표시 됩니다. Microsoft Managed Desktop administration portal은 보기를 Windows 10 응용 프로그램으로 제한 합니다. 둘 다 Azure Portal을 통해 사용할 수 있습니다. 
* [Intune 앱 관리 기본 사항](https://docs.microsoft.com/intune/app-management)
* [Intune에 앱 추가](https://docs.microsoft.com/intune/app-management)
   * [기간 업무 (lob) 앱 추가](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Intune에 Win32 앱 추가](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [웹 응용 프로그램 추가](https://docs.microsoft.com/intune/web-app)
* [앱 배포](https://docs.microsoft.com/intune/apps-deploy)
   * [Windows 10에 앱 배포](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* 회사 포털
   * [회사 포털 배포](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [회사 포털 앱 구성](https://docs.microsoft.com/intune/company-portal-app)
