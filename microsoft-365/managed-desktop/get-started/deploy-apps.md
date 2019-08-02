---
title: Microsoft Managed Desktop devices 용 앱 배포
description: Microsoft Managed Desktop 장치에 앱을 추가 및 배포 하기 위한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB (기간 업무) 앱, 업무용 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e842849afbedd506689caa9ffc0953a58e18fed
ms.sourcegitcommit: f5c9aff5700f7824bf71f4a7e8c7236f7d91043e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2019
ms.locfileid: "36059588"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Microsoft Managed Desktop 장치에 앱 배포
Microsoft Managed Desktop 온 보 딩에는 사용자의 장치에 앱을 추가 및 배포 하는 작업이 포함 됩니다. Microsoft Managed Desktop portal을 사용 하 고 나면 앱을 추가 및 배포할 수 있습니다. 

전체 프로세스는 다음과 같습니다.
1. [Microsoft Managed Desktop portal에 앱 추가](#1) -이는 기존 LOB (기간 업무) 앱 이거나 Intune을 사용 하 여 동기화 한 Microsoft Store 비즈니스용 앱이 될 수 있습니다. 
2. [앱 할당에 대 한 AZURE AD (Active Directory) 그룹 만들기](#2) -이러한 그룹을 사용 하 여 앱 할당을 관리 합니다.
3. [사용자에 게 앱 할당](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>1 단계: Microsoft Managed Desktop portal에 앱 추가
[Win32 또는 WINDOWS MSI 기반 앱](#lob-apps)또는 [비즈니스용 Microsoft Store for Business Apps](#msfb-apps) 를 microsoft managed desktop에 추가한 다음이를 microsoft managed desktop 장치에 배포할 수 있습니다.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Microsoft Managed Desktop에 대 한 Win32 또는 Windows MSI 기반 앱

기간 업무 (LOB) 앱을 Microsoft Managed Desktop portal에 추가할 수 있습니다. Microsoft Managed Desktop 장치에 설치 된 앱에 대 한 요구 사항에 대 한 자세한 내용은 [Microsoft Managed desktop app 요구 사항을](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)참조 하세요.

이 절차에서는 추가 하려는 앱의 종류를 선택한 다음 앱 원본을 구성 및 업로드 합니다. 

**Microsoft Managed Desktop portal에 LOB 앱 또는 Windows 앱을 추가 하려면**

Microsoft Managed Desktop portal에 로그인 하거나 Intune에 로그인 한 다음 Microsoft Managed Desktop을 검색할 수 있습니다. Microsoft Managed Desktop portal에 로그인을 표시 합니다. 

1.  [Microsoft Managed 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다. 
2.  **인벤토리에서** **앱**을 선택 합니다.
3.  앱 작업에서 **추가**를 선택 합니다.
4.  **앱 추가**에서 lob ( **기간 업무) 앱** 또는 **Windows 앱 (Win32)** 을 선택 합니다.
    - **기간 업무**(lob) 앱을 선택한 경우 lob (기간 업무) 앱 추가 및 구성에 대 한 지침을 보려면 [Microsoft Intune에 Windows lob (기간 업무) 앱 추가](https://docs.microsoft.com/intune/lob-apps-windows) 를 참조 하세요.
    - **Windows 앱 (win32)** 을 선택한 경우 windows 앱 추가 및 구성에 대 한 지침은 [win32 앱 관리](https://docs.microsoft.com/intune/apps-win32-app-management) 를 참조 하세요.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store for Business 앱
Microsoft Store for Business에 등록 하지 않은 경우 앱을 쇼핑 하면 등록할 수 있습니다. 앱을 설치한 후에는 Microsoft Managed Desktop과 동기화 할 수 있습니다. 

**Microsoft Store for Business에서 앱을 구입 하려면**

1. 비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.
2. **내 그룹의 상점을**선택 합니다.
3. 검색을 사용 하 여 원하는 앱을 찾은 다음 앱을 선택 합니다.
4. 제품 정보에서 **앱 가져오기를**선택 합니다. Microsoft Store에서는 조직의 **제품 & 서비스** 에 앱을 추가 합니다.

**Intune과 비즈니스용 Microsoft Store를 강제 동기화 하려면**
1. 테 넌 트에 대 한 Intune 관리자 또는 전역 관리자로 [Azure 포털](https://portal.azure.com/) 에 로그인 합니다.
2. **모든 서비스 > Intune**을 선택 합니다. Intune은 모니터링 + 관리 섹션에 있습니다.
3. Intune 창에서 **클라이언트 앱**을 선택 하 고 **Microsoft Store for Business**를 선택 합니다.
4. Intune을 사용 하 여 비즈니스 앱 용 Microsoft Store를 동기화 하려면 **사용** 을 선택 합니다.
    - 아직 설치 하지 않은 경우 Intune을 사용 하 여 Microsoft Store for Business 계정을 등록 및 연결 합니다.
    - Microsoft Store for Business 앱이 Intune 콘솔에 표시 되는 언어 선택
    - **동기화** 를 선택 하 여 비즈니스용 Microsoft 스토어 앱 for Intune을 동기화 합니다.
    - Microsoft Store for Business 및 Intune 간의 동기화가 활성 상태 인지 확인 합니다 (다음 단계). 

**Intune과 비즈니스용 Microsoft Store 간의 동기화가 활성 상태 인지 확인 하려면**
1. 비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.
2. **관리**를 선택 합니다.
3. **설정을** 선택 하 고 **배포**를 선택 합니다.
4. **관리 도구**에서 Intune이 나열 되는지와 상태가 **활성**상태 인지 확인 합니다.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>2 단계: Azure AD 그룹 만들기

각 앱에 대해 세 개의 Azure AD 그룹을 만듭니다. 이 표에는 필요한 그룹 (사용 가능, 필수 및 제거)이 정리 되어 있습니다. 

앱 할당 유형 |   그룹 사용   | 예제 Azure AD 이름
--- | --- | ---
사용할 수 있음 |  이 앱은 회사 포털 앱 또는 웹 사이트에서 사용할 수 있습니다. | MMD- *응용 프로그램 이름* -사용 가능
필수 |  앱이 선택한 그룹의 장치에 설치 되어 있습니다. | MMD- *응용 프로그램 이름* -필수
Uninstall |  창의 앱이 선택한 그룹의 장치에서 제거 되었습니다. | MMD- *응용 프로그램 이름* -제거

이러한 그룹에 사용자를 추가 하 여 앱을 availabe, 앱을 설치 하거나, Microsoft Managed Desktop 장치에서 앱을 제거 합니다. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>3 단계: 사용자에 게 앱 할당

**사용자에 게 앱을 할당 하려면**

1. [Microsoft Managed 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다.
2. 관리 되는 데스크톱 창에서 **앱**을 선택 합니다.
3. 앱 작업에서 사용자를 할당 하려는 앱을 선택 하 고 **사용자 그룹 할당**을 선택 합니다.
4. 특정 앱에 대해 할당 유형 (사용 가능, 필수, 제거)을 선택 하 고 적절 한 그룹을 할당 합니다.
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
