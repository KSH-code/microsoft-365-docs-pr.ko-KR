---
title: 관리 되는 데스크톱 앱을 준비 하 고 Microsoft에 대 한
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: ebeb54bd5d1f50cbb6f78b1c8ad4a624c449b8c2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869922"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>관리 되는 데스크톱 앱을 준비 하 고 Microsoft에 대 한

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Microsoft 및 데스크톱을 관리 하는 Microsoft 고객 중심으로 데스크톱을 관리 하는 Microsoft와 함께 사용 하는 응용 프로그램의 중요 한, 아직 다른 책임은 동일 하 게 되었습니다.

## <a name="microsoft-responsibilites"></a>Microsoft responsibilites
**Office 365 앱** Microsoft는 배포, 업데이트 및 특정 Office 365 앱의 지원에 대 한 전체 서비스를 제공 합니다. 모든 사용자에 게 사용자 생산성을 신속 하 게 될 수 있도록 장치의 이미지에 포함 된 응용 프로그램의 64 비트 버전을 실행 하려면 Office 365의 기본 집합을 받게 됩니다. 프로젝트 및 Visio 응용 프로그램에서 Office 365 제품군의는 별도로 사용이 허가 됩니다.  Microsoft 관리 되는 데스크톱은 IT 관리자에 게 라이선스를 관리 하 고 이러한 응용 프로그램을 조직에 적절 하 게 배포를 허용 하는 배포 그룹을 제공 합니다. Microsoft는 Microsoft 관리 되는 데스크톱 지원 채널을 통해 이러한 응용 프로그램의 최종 사용자를 지원 합니다.

**비즈니스 라인 앱** Microsoft IT 관리자가 Intune 제품의 일부로 최종 사용자에 게 해당 줄의 비즈니스 응용 프로그램을 배포 및 관리 도구를 제공 합니다. Microsoft는 [비즈니스 라인 응용 프로그램](#line-of-business-applications) 에서 설명한 대로 배포 문제를 응용 프로그램을 지원 

**Intune를 사용 하 여 배포** Intune는 Microsoft 관리 되는 데스크톱 온 보 딩 확보 앱 Intune를 통해 배포할 수 있도록 허용 하는 동안 **비즈니스를 위한 Microsoft 저장소** 에 연결 됩니다. Microsoft IT 관리자가 최종 사용자에 대 한 셀프서비스 경험을 제공할 수 있도록 최종 사용자에 게 웹 기반 버전의 회사 포털 배포도 됩니다.

**응용 프로그램 관리** Microsoft는 자신의 시스템 영향으로 인해 현대 직장에 적합 하지 않은 제한 된 응용 프로그램을 식별할 수 있습니다. 이러한 응용 프로그램 식별 되는 Microsoft 고객 알림을 생성 하는 하 고 해당 응용 프로그램 테 넌 트에서 제거 해야 합니다. 

## <a name="customer-responsibilities"></a>고객 책임
Office 365 제품군 Microsoft의 생산성 제품의 필수 요소 이며 모든 Microsoft 관리 되는 데스크톱 사용자에 대 한 Microsoft 365 라이선스에 포함 됩니다. Microsoft 배포, 업데이트 하 고 데스크톱 장치를 관리 하는 Microsoft Office 응용 프로그램을 지원 하는 동안 가지 여전히 일부 고객은 책임을 집니다.
- **라이선스 할당** -고객에 게는 Office 365에 대 한 최종 사용자에 게 적절 한 라이선스를 할당 하는 일을 담당 합니다. 
- **보안 그룹에 사용자 추가** -사용자와 프로젝트 또는 Visio, 고객에 대 한 IT 관리자가 해당 사용자를 추가 해야 적절 한 배포 그룹입니다. IT 관리자가 해당 사용자에 대 한 제공 종료를 관리 하기 위한도 책임이 있습니다. 
- **Office 365 추가 기능 배포** -고객에 게는 모든 플러그인 필요한 것으로 간주 되는 Office 365 제품군을 배포 하는 일을 담당 합니다. 

비즈니스 라인 (lob 기간 업무) 응용 프로그램은 각 고객에 대 한 고유, 고객은 Microsoft에 의해 배포 되지 않은 조직 내에서 모든 응용 프로그램 관리를 담당 합니다. 이는 다음이 포함 됩니다.
- 앱 필요 하 고 필요한 사용자를 결정 합니다.
- 앱 해당 사용자에 게 할당
- 작성 및 응용 프로그램 할당을 관리 하기 위한 Azure Active Directory (AD) 그룹을 유지 관리 

LOB 응용 프로그램의 핵심 집합 식별 된 후 고객을 조달, 라이선스, 패키지 하 고, 및 Microsoft 관리 되는 데스크톱 환경에서 해당 응용 프로그램을 테스트 합니다. 고객을 업로드 하 고 배포 하 고 업데이트 하 고, 해당 LOB 응용 프로그램을 해제 하는 Intune 응용 프로그램을 배포 해야 합니다. 고객에 게는 해당 사용자에 대 한 LOB 응용 프로그램 지원 관리를 담당 합니다.
 

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

## <a name="resources"></a>리소스
Microsoft 관리 되는 데스크톱 작업에 대 한 범위 바깥에 다양 한 서비스 하는 동안에 해당 응용 프로그램을 관리 하는 고객은 데 도움이 되는 Microsoft 기능을 제공 하는 서비스입니다.

### <a name="windows-upgrade-readiness"></a>Windows 업그레이드 준비
새 Microsoft 관리 되는 장치 설정의 핵심 요소는 앱 장치 사용자를 위해 필요한 이해입니다. Windows 업그레이드 준비는 기업이 자신의 회사 내 응용 프로그램 가로 이해 하는데 도움이 됩니다 하 수와 같은 해당 응용 프로그램에 대 한 키 데이터를 검토할 수 있도록 도와주는 Microsoft 도구:

- **응용 프로그램의 사용량이** -원격 분석 데이터를 사용 하 여 응용 프로그램 사용을 모니터링 합니다.
- **응용 프로그램 호환성** -업그레이드 준비 방법 광범위 하 게 배포한 최신 버전의 Windows 10에서 볼 수 및 "준비에 대 한 Windows" 인지 확인 하는 방법을 평가 각 응용 프로그램을 확인 합니다. 이 데이터는 집중적으로 테스트 활동을 이미 광범위 하 게 채택 되지 않은 응용 프로그램에 도움이 됩니다.

### <a name="intune-application-deployment"></a>Intune 응용 프로그램 배포
Microsoft 관리 되는 데스크톱 관리 포털을 통해 또는 Intune 포털을 통해 응용 프로그램 관리를 처리할 수 있습니다. Intune의 응용 프로그램 관리 포털, Android, 창과 iOS에 대 한 배포 하는 응용 프로그램을 보여줍니다. Microsoft 관리 되는 데스크톱 관리 포털 Windows 10 응용 프로그램에 대 한 보기를 제한합니다. 두 가지 Azure 포털을 통해 사용할 수 있습니다. 
- [Intune 응용 프로그램 관리 기본 사항](https://docs.microsoft.com/intune/app-management)
- [Windows 32 응용 프로그램을 추가 합니다.](https://docs.microsoft.com/intune/lob-apps-windows)
- [웹 응용 프로그램 추가](https://docs.microsoft.com/intune/web-app)
- [지정 하 고 그룹에 응용 프로그램 배포](https://docs.microsoft.com/intune/apps-deploy)

### <a name="application-packaging-standards"></a>응용 프로그램 패키지 표준
있어야 Intune 통해 Windows 32 응용 프로그램을 배포 하는 단일 하나으로 패키지 합니다. MSI는.appx 또는 합니다. MSIX 합니다. Intune에 대 한 가장 일반적인 패키지 종류는 현재. MSI 합니다.
