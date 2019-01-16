---
title: 관리 되는 데스크톱 앱을 준비 하 고 Microsoft에 대 한
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869922"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>관리 되는 데스크톱 앱을 준비 하 고 Microsoft에 대 한

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Microsoft 및 데스크톱을 관리 하는 Microsoft 고객 중심으로 데스크톱을 관리 하는 Microsoft와 함께 사용 하는 응용 프로그램의 중요 한, 아직 다른 책임은 동일 하 게 되었습니다.

## <a name="microsoft-responsibilities"></a>Microsoft의 업무
**Office 365 앱** Microsoft는 배포, 업데이트 및 특정 Office 365 앱의 지원에 대 한 전체 서비스를 제공 합니다. 모든 사용자에 게 사용자 생산성을 신속 하 게 될 수 있도록 장치의 이미지에 포함 된 응용 프로그램의 64 비트 버전을 실행 하려면 Office 365의 기본 집합을 받게 됩니다. 프로젝트 및 Visio 응용 프로그램에서 Office 365 제품군의는 별도로 사용이 허가 됩니다.  Microsoft 관리 되는 데스크톱은 IT 관리자에 게 라이선스를 관리 하 고 이러한 응용 프로그램을 조직에 적절 하 게 배포를 허용 하는 배포 그룹을 제공 합니다. Microsoft는 Microsoft 관리 되는 데스크톱 지원 채널을 통해 이러한 응용 프로그램의 최종 사용자를 지원 합니다.

**비즈니스 라인 앱** Microsoft IT 관리자가 Intune 제품의 일부로 최종 사용자에 게 자신의 기간 업무 (LOB) 응용 프로그램을 배포 및 관리 도구를 제공 합니다. Microsoft는 [비즈니스 라인 응용 프로그램](#line-of-business-applications) 에서 설명한 대로 배포 문제를 응용 프로그램을 지원 

**Intune를 사용 하 여 배포** Intune는 Microsoft 관리 되는 데스크톱 온 보 딩 확보 앱 Intune를 통해 배포할 수 있도록 허용 하는 동안 **비즈니스를 위한 Microsoft 저장소** 에 연결 됩니다. Microsoft IT 관리자가 최종 사용자에 대 한 셀프서비스 경험을 제공할 수 있도록 최종 사용자에 게 웹 기반 버전의 회사 포털 배포도 됩니다.

**응용 프로그램 관리** Microsoft는 자신의 시스템 영향으로 인해 현대 직장에 적합 하지 않은 제한 된 응용 프로그램을 식별할 수 있습니다. 이러한 응용 프로그램 식별 되는 Microsoft 고객 알림을 생성 하는 하 고 해당 응용 프로그램 테 넌 트에서 제거 해야 합니다. 

제한 된 응용 프로그램 동작 및 응용 프로그램 요구 사항에 대 한 자세한 내용은 [Microsoft 관리 되는 데스크톱 응용 프로그램 요구 사항](../service-description/mmd-app-requirements.md) 을 참조 하십시오.

## <a name="customer-responsibilities"></a>고객 책임
Office 365 제품군 Microsoft의 생산성 제품의 필수 요소 이며 모든 Microsoft 관리 되는 데스크톱 사용자에 대 한 Microsoft 365 라이선스에 포함 됩니다. Microsoft 배포, 업데이트 하 고 데스크톱 장치를 관리 하는 Microsoft Office 응용 프로그램을 지원 하는 동안 가지 여전히 일부 고객은 책임을 집니다.
- **라이선스 할당** -고객에 게는 Office 365에 대 한 최종 사용자에 게 적절 한 라이선스를 할당 하는 일을 담당 합니다. 
- **보안 그룹에 사용자 추가** -사용자와 프로젝트 또는 Visio, 고객에 대 한 IT 관리자가 해당 사용자를 추가 해야 적절 한 배포 그룹입니다. IT 관리자가 해당 사용자에 대 한 제공 종료를 관리 하기 위한도 책임이 있습니다. 
- **Office 365 추가 기능 배포** -고객에 게는 모든 플러그인 필요한 것으로 간주 되는 Office 365 제품군을 배포 하는 일을 담당 합니다. 

비즈니스 라인 (lob 기간 업무) 응용 프로그램은 각 고객에 대 한 고유, 고객은 Microsoft에 의해 배포 되지 않은 조직 내에서 모든 응용 프로그램 관리를 담당 합니다. 이는 다음이 포함 됩니다.
- 앱 필요 하 고 필요한 사용자를 결정 합니다.
- 앱 해당 사용자에 게 할당
- 작성 및 응용 프로그램 할당을 관리 하기 위한 Azure Active Directory (AD) 그룹을 유지 관리 

고객은 Intune를 LOB 응용 프로그램을 업로드 해야 합니다. 배포, 업데이트 하 고 자신의 개별 수명 주기를 통해 해당 응용 프로그램을 해제 뿐아니라 사용자에 게 이러한 앱에 대 한 지원을 관리 하는 일을 담당 하는 다음 합니다.

## <a name="office-applications"></a>Office 응용 프로그램
Microsoft 365 E5 라이선스의 일부로 Office 365 표준 도구 모음 (64 비트)는 Microsoft에서 배포 됩니다. 

자세한 내용은 [Microsoft 관리 되는 데스크톱 기술](../intro/technologies.md) 참조<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>비즈니스 라인 응용 프로그램
이 표에서 비즈니스 라인 (lob 기간 업무) 응용 프로그램에 대 한 서로 다른 단계에서 책임을 요약합니다. 

응용 프로그램 작업 항목 |    고객    | Microsoft
--- | --- | ---
**온 보 딩 앱** |  |
대상된 사용자 그룹에 필요한 응용 프로그램을 식별 합니다.   | ![예](images/checkmark.png)  |
응용 프로그램 배포를 위한 Azure AD 그룹 만들기 및 관리 | ![예](images/checkmark.png) |   
**응용 프로그램 패키지** |  |
Intune 배포 표준을 충족 하기 위해 패키지 앱 |  ![예](images/checkmark.png) |  
Intune에 앱을 업로드 합니다. | ![예](images/checkmark.png)     |
Microsoft 관리 되는 데스크톱 환경에서 앱을 테스트 합니다. |    ![예](images/checkmark.png) |  
최종 사용자와 함께 응용 프로그램 테스트    | ![예](images/checkmark.png) |    
**배포** | |
관리 및 응용 프로그램에 사용자 할당  | ![예](images/checkmark.png)  |
원격 클라이언트에 응용 프로그램을 제공 하는 Intune 배포 도구| |   ![예](images/checkmark.png)
식별 하 고 Intune 통해 응용 프로그램 업데이트 배포 | ![예](images/checkmark.png)    |
사용 되지 않은 경우 설치 제거 하 고 제거 응용 프로그램    | ![예](images/checkmark.png) |    
**관리** | |
조달 및 라이선스 할당 |   ![예](images/checkmark.png)     |
비즈니스 라인 앱에 대 한 최종 사용자 지원 제공  | ![예](images/checkmark.png) |
응용 프로그램 설정 관리 원격으로    | ![예](images/checkmark.png) |

LOB 응용 프로그램 요구 사항에 대 한 정보를 [Microsoft 관리 되는 데스크톱 응용 프로그램 요구 사항](../service-description/mmd-app-requirements.md) 을 참조 하십시오.


## <a name="intune-application-deployment"></a>Intune 응용 프로그램 배포
Microsoft 관리 되는 데스크톱 관리 포털을 통해 또는 Intune 포털을 통해 응용 프로그램 관리를 처리할 수 있습니다. Intune의 응용 프로그램 관리 포털, Android, 창과 iOS에 대 한 배포 하는 응용 프로그램을 보여줍니다. Microsoft 관리 되는 데스크톱 관리 포털 Windows 10 응용 프로그램에 대 한 보기를 제한합니다. 두 가지 Azure 포털을 통해 사용할 수 있습니다. 
* [Intune 응용 프로그램 관리 기본 사항](https://docs.microsoft.com/intune/app-management)
* [Intune에 앱 추가](https://docs.microsoft.com/intune/app-management)
   * [비즈니스 라인 응용 프로그램을 추가 합니다.](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Intune에 Win32 앱 추가](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [웹 응용 프로그램 추가](https://docs.microsoft.com/intune/web-app)
* [응용 프로그램 배포](https://docs.microsoft.com/intune/apps-deploy)
   * [Windows 10에 앱을 배포 합니다.](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* 회사 포털
   * [회사 포털 배포](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [회사 포털 응용 프로그램 구성](https://docs.microsoft.com/intune/company-portal-app)
