---
title: 장치에 앱 배포
description: Microsoft Managed Desktop 장치에 앱을 추가 및 배포 하기 위한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB (기간 업무) 앱, 업무용 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769109"
---
# <a name="deploy-apps-to-devices"></a>장치에 앱 배포
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

1.    [Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mmdportal)에 로그인 합니다. 
2.    **인벤토리에서** **앱** 을 선택 합니다.
3.    앱 작업에서 **추가** 를 선택 합니다.
4.    **앱 추가** 에서 lob ( **기간 업무) 앱** 또는 **Windows 앱 (Win32)** 을 선택 합니다.
    - **기간 업무** (lob) 앱을 선택한 경우 lob (기간 업무) 앱 추가 및 구성에 대 한 지침을 보려면 [Microsoft Intune에 Windows lob (기간 업무) 앱 추가](https://docs.microsoft.com/intune/lob-apps-windows) 를 참조 하세요.
    - **Windows 앱 (win32)** 을 선택한 경우 windows 앱 추가 및 구성에 대 한 지침은 [win32 앱 관리](https://docs.microsoft.com/intune/apps-win32-app-management) 를 참조 하세요.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store for Business 앱
Microsoft Store for Business에 등록 하지 않은 경우 앱을 쇼핑 하면 등록할 수 있습니다. 앱을 설치한 후에는 Microsoft Managed Desktop과 동기화 할 수 있습니다. 

**Microsoft Store for Business에서 앱을 구입 하려면**

1. 비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.
2. **내 그룹의 상점을** 선택 합니다.
3. 검색을 사용 하 여 원하는 앱을 찾은 다음 앱을 선택 합니다.
4. 제품 정보에서 **앱 가져오기를** 선택 합니다. Microsoft Store에서는 조직의 **제품** 에 앱이 추가 됩니다.

**Intune과 비즈니스용 Microsoft Store를 강제 동기화 하려면**
1. [Microsoft Endpoint Manager 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431)에 로그인 합니다.
2. 비즈니스용 **테 넌 트 관리**  >  **커넥터 및 토큰**  >  **Microsoft Store** 를 선택 합니다.
3. **동기화** 를 선택 하 여 Microsoft Store에서 구입한 앱을 Intune으로 가져옵니다.

**Intune과 비즈니스용 Microsoft Store 간의 동기화가 활성 상태 인지 확인 하려면**
1. 비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.
2. **관리** 를 선택 합니다.
3. **설정을** 선택 하 고 **배포** 를 선택 합니다.
4. **관리 도구** 에서 Intune이 나열 되는지와 상태가 **활성** 상태 인지 확인 합니다.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>2 단계: Azure AD 그룹 만들기

각 앱에 대해 세 개의 Azure AD 그룹을 만듭니다. 이 표에는 필요한 그룹 (사용 가능, 필수 및 제거)이 정리 되어 있습니다. 

앱 할당 유형 |    그룹 사용    | 예제 Azure AD 이름
--- | --- | ---
사용할 수 있음 |  이 앱은 회사 포털 앱 또는 웹 사이트에서 사용할 수 있습니다. | MMD- *응용 프로그램 이름* -사용 가능
필수 |  앱이 선택한 그룹의 장치에 설치 되어 있습니다. | MMD- *응용 프로그램 이름* -필수
Uninstall |  앱이 선택한 그룹의 장치에서 제거 되었습니다. | MMD- *응용 프로그램 이름* -제거

이러한 그룹에 사용자를 추가 하 여 앱을 사용할 수 있도록 설정 하거나, 앱을 설치 하거나, Microsoft Managed Desktop 장치에서 앱을 제거 합니다. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>3 단계: 사용자에 게 앱 할당

**사용자에 게 앱을 할당 하려면**

1. [Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mmdportal)에 로그인 합니다.
2. 관리 되는 데스크톱 창에서 **앱** 을 선택 합니다.
3. 앱 작업에서 사용자를 할당 하려는 앱을 선택 하 고 **사용자 그룹 할당** 을 선택 합니다.
4. 특정 앱에 대해 할당 유형 (사용 가능, 필수, 제거)을 선택 하 고 적절 한 그룹을 할당 합니다.
5. 앱 할당 창에서 **확인** 을 선택 합니다.


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털에서 관리자 연락처 추가 및 확인](add-admin-contacts.md)
2. [조건부 액세스 조정](conditional-access.md)
3. [라이선스 할당](assign-licenses.md)
4. [Intune 회사 포털 배포](company-portal.md)
5. [엔터프라이즈 상태 로밍 사용](enterprise-state-roaming.md)
6. [장치 설정](set-up-devices.md)
7. [사용자들이 장치를 사용할 수 있도록 준비시키기](get-started-devices.md)
8. 앱 배포 (이 항목)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
