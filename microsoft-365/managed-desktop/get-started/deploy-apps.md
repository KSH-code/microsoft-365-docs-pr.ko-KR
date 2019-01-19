---
title: Microsoft 관리 되는 데스크톱 장치에 대 한 앱 배포
description: 추가 (영문) 및 Microsoft 관리 되는 데스크톱 장치에 앱을 배포에 대 한 정보를 제공 합니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365, 서비스, 설명서, 앱, 비즈니스 라인 앱, LOB 응용 프로그램
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341615"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Microsoft 관리 되는 데스크톱 장치에 앱을 배포 합니다.
Microsoft 관리 되는 데스크톱에 온 보 딩 부분에서는 사용자의 장치에 앱을 배포 하 고 추가 (영문)를 포함 합니다. Microsoft 관리 되는 데스크톱 포털을 사용 하는 추가 하 고 앱을 배포할 수 있습니다. 

전체 프로세스는 다음과 같습니다.
1. [Microsoft 관리 되는 데스크톱 포털에 추가 앱](#1) -비즈니스 라인 (lob 기간 업무) 응용 프로그램이 또는 Intune 사용한 동기화 했을 때 비즈니스를 위한 Microsoft 저장소에서 앱이 기존 될 수 있습니다. 
2. [응용 프로그램 할당에 대 한 만들기 Azure Active Directory (AD) 그룹](#2) -app 배정 관리 이러한 그룹을 사용 합니다.
3. [앱 사용자에 게 할당](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>1 단계: 관리 되는 데스크톱 Microsoft 포털에 앱 추가
Microsoft 관리 되는 데스크톱에 [Win32 또는 Windows MSI 기반 앱](#lob-apps), 또는 [비즈니스 응용 프로그램에 대 한 Microsoft 저장소](#msfb-apps) 를 추가할 수 있으며 Microsoft 관리 되는 데스크톱 장치에 배포 합니다.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 또는 Windows MSI 기반 앱을 Microsoft 데스크톱 관리

Microsoft 관리 되는 데스크톱 포털에 비즈니스 라인 (lob 기간 업무) 응용 프로그램을 추가할 수 있습니다. Microsoft 관리 되는 데스크톱 장치에 설치 된 앱에 대 한 요구 사항에 대 한 정보를 [Microsoft 관리 되는 데스크톱 응용 프로그램 요구 사항](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)을 참조 하십시오.

이 절차를 추가 하 고 다음 구성 및 응용 프로그램 소스를 업로드 하려는 응용 프로그램의 종류를 선택 합니다. 

**Microsoft 관리 되는 데스크톱 포털에 LOB 응용 프로그램 또는 Windows 응용 프로그램을 추가 하려면**

Microsoft 관리 되는 데스크톱 포털에 로그인 하 고 또는 Intune에 로그인 하 고, Microsoft 관리 되는 데스크톱에 대 한 다음 검색 수 있습니다. Microsoft 관리 되는 데스크톱 포털에 로그인 살펴보겠습니다. 

1.  [Microsoft 관리 되는 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다. 
2.  **재고** **앱**을 선택 합니다.
3.  앱 작업에서 **추가**선택 합니다.
4.  **추가 응용 프로그램** **비즈니스 라인 응용 프로그램** 또는 **Windows 응용 프로그램 (Win32)-미리 보기**를 선택 합니다.
    - **비즈니스 라인 응용 프로그램**을 선택한 경우 추가 (영문) 및 비즈니스 라인 앱 구성에 대 한 지침은 [Microsoft Intune 하는 Windows 비즈니스 라인 앱 추가](https://docs.microsoft.com/intune/lob-apps-windows) 참조 합니다.
    - **Windows 응용 프로그램 (Win32)-미리 보기**를 선택한 경우 추가 (영문) 및 Windows 앱 구성에 대 한 지침은 [Win32 응용 프로그램 관리](https://docs.microsoft.com/intune/apps-win32-app-management) 를 참조 하십시오.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>비즈니스 응용 프로그램에 대 한 Microsoft 저장소
비즈니스를 위한 Microsoft 저장소와 가입 하지 않은 경우 앱에 대 한 쇼핑을 할 때 서명할 수 있습니다. 앱을 설치한 후 Microsoft 관리 데스크톱과 동기화 할 수 있습니다. 

**비즈니스를 위한 Microsoft 스토어의 앱 구입**

1. [비즈니스를 위한 Microsoft 저장소](https://businessstore.microsoft.com) 를 비즈니스 관리자 계정에 대 한 Microsoft 저장소와에 로그인 합니다.
2. **내 그룹에 대 한 상점**을 선택 합니다.
3. 검색을 사용 하 여 원하는 앱을 파악 하 고 응용 프로그램을 선택 합니다.
4. 제품 세부 정보에서 **앱**을 선택 합니다. Microsoft 저장소를 사용 하면 **제품 & 서비스** 에 앱을 추가 하는 조직에 대 한입니다.

**Intune 및 비즈니스를 위한 Microsoft 저장소 간의 동기화를 강제로 실행 하려면**
1. 테 넌 트에 대 한 Intune 관리자 또는 전역 관리자도 [Azure 포털](https://portal.azure.com/) 로그인
2. **모든 서비스 gt_ Intune를**선택 합니다. Intune 모니터링 + 관리에는 섹션입니다.
3. Intune 창에서 **클라이언트 응용 프로그램**선택 하 고 **비즈니스를 위한 Microsoft 저장소**를 선택 합니다.
4. Intune 사용한 비즈니스 응용 프로그램에 대 한 사용자 Microsoft 저장소를 동기화 할 **사용** 을 선택 합니다.
    - 이미 하지 않은 경우 로그인 및 연결 Microsoft 저장 Intune 사용한 비즈니스 계정에 대 한
    - Intune 콘솔에서 비즈니스를 위한 Microsoft 스토어 앱 표시 될 언어를 선택 합니다.
    - Intune 사용한 비즈니스 응용 프로그램에 대 한 사용자 Microsoft 저장소를 동기화 할 **동기화** 선택 합니다.
    - 비즈니스를 위한 Microsoft 저장소와 Intune 간에 동기화 활성화 되었는지 확인 (다음 단계). 

**Intune 및 비즈니스를 위한 Microsoft 저장소 간의 동기화를 활성화 되었는지 확인 하려면**
1. [비즈니스를 위한 Microsoft 저장소](https://businessstore.microsoft.com) 를 비즈니스 관리자 계정에 대 한 Microsoft 저장소와에 로그인 합니다.
2. **관리**를 선택 합니다.
3. **설정** 을 선택 하 고 **배포**를 선택 합니다.
4. **관리 도구**Intune 표시 되 고 **활성**상태 인지 확인 합니다.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>2 단계: Azure AD 그룹 만들기

각 응용 프로그램에 대 한 세 Azure AD 그룹을 만듭니다. 이 표에서 필요한 그룹을 대략적으로 보여줍니다 (대화 가능, 필요한 한 제거)를 클릭 합니다. 

App 배정 종류 |   그룹 사용   | 예제 Azure AD 이름
--- | --- | ---
사용 가능 |  응용 프로그램은 회사 포털 응용 프로그램 또는 웹 사이트에서 사용할 수 있습니다. | MMD- *응용 프로그램 이름* -가능
필수 |  앱이 선택된 된 그룹에 장치에 설치 합니다. | MMD- *응용 프로그램 이름* -필요 합니다.
선택하여 |  삭제할 app은 선택한 그룹에 장치에서 제거 됩니다. | MMD- *응용 프로그램 이름* -제거

App 사용할 수 있는 확인, 앱을 설치 하거나 자신의 데스크톱을 관리 하는 Microsoft 장치에서 응용 프로그램을 제거 하려면 이러한 그룹에 사용자를 추가 합니다. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>3 단계: 응용 프로그램을 사용자에 게 할당

**응용 프로그램 사용자에 게 할당 하려면**

1. [Microsoft 관리 되는 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다.
2. 관리 되는 데스크톱 창에서 **앱**을 선택 합니다.
3. 앱 작업에서 **사용자 그룹에 할당**을 선택 하 고 사용자에 게 할당 하려는 앱을 선택 합니다.
4. 특정 응용 프로그램에 대 한 배정 종류 (대화 가능, 필요한 제거)를 선택 하 고 적절 한 그룹을 할당 합니다.
5. 앱 할당 창에서 **확인**을 선택 합니다.

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->