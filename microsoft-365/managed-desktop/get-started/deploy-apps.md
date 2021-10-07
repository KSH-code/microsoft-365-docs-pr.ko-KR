---
title: 장치에 앱 배포
description: 디바이스에 앱을 추가하고 배포하는 Microsoft Managed Desktop 정보입니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB 앱, LOB 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a84f6e13a7c189ce4cd33f308e765e5c59dae374
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195236"
---
# <a name="deploy-apps-to-devices"></a>장치에 앱 배포
온보드를 Microsoft Managed Desktop 장치에 앱을 추가하고 배포하는 것이 포함됩니다. 앱 포털을 Microsoft Managed Desktop 앱을 추가하고 배포할 수 있습니다. 

전체 프로세스는 다음과 같습니다.
1. [Microsoft Managed Desktop](#1) 포털에 앱 추가 - 기존 LOB(LOB) 앱 또는 Intune과 동기화한 비즈니스용 Microsoft Store 앱일 수 있습니다. 
2. [앱 Azure Active Directory AD(서비스)](#2) 그룹 만들기 - 이러한 그룹을 사용하여 앱 할당을 관리합니다.
3. [사용자에게 앱 할당](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>1단계: 포털에 Microsoft Managed Desktop 추가
[Win32를](#lob-apps)추가하거나 MSI Windows 앱을 추가하거나 [](#msfb-apps) 비즈니스용 Microsoft Store 앱을 Microsoft Managed Desktop 디바이스에 배포할 Microsoft Managed Desktop 있습니다.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 또는 Windows MSI 기반 앱을 사용하여 Microsoft Managed Desktop

LOB(LOB) 앱을 포털에 추가할 Microsoft Managed Desktop 있습니다. Microsoft Managed Desktop 앱 요구 사항에 대한 자세한 내용은 앱 요구 [Microsoft Managed Desktop 참조하세요.](../service-description/mmd-app-requirements.md)

이 절차에서는 추가할 앱 종류를 선택한 다음 앱 원본을 구성 및 업로드합니다. 

**LOB 앱 또는 Windows 포털에 Microsoft Managed Desktop 추가**

포털에 로그인하거나 Microsoft Managed Desktop 로그인한 다음 검색을 Microsoft Managed Desktop. 이 포털에 로그인하는 Microsoft Managed Desktop 있습니다. 

1.    관리자 포털 [Microsoft Managed Desktop 로그인합니다.](https://aka.ms/mmdportal) 
2.    **인벤토리에서** 앱을 **선택합니다.**
3.    앱 작업에서 추가를 **선택합니다.**
4.    앱 **추가에서** **LINE-OF-BUSINESS 앱** 또는 Windows **앱(Win32)을 선택합니다.**
    - 업무용 앱 추가 및 구성에 [](/intune/lob-apps-windows) 대한 지침은 WINDOWS 앱 추가를 참조하여 Microsoft Intune 앱을 추가하고 구성하는 데 필요한 지침은 추가를 참조하세요.
    - **앱(win32)Windows** 선택한 경우 [Win32](/intune/apps-win32-app-management) 앱 관리를 참조하여 앱 추가 및 구성에 대한 Windows 참조하세요.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>비즈니스용 Microsoft Store 앱
앱에 등록하지 않은 비즈니스용 Microsoft Store 앱을 구매할 때 등록할 수 있습니다. 앱을 다운로드한 후 앱과 동기화할 Microsoft Managed Desktop. 

**앱에서 앱을 구입 비즈니스용 Microsoft Store**

1. 비즈니스용 Microsoft Store 관리자 [계정으로](https://businessstore.microsoft.com) 비즈니스용 Microsoft Store 로그인합니다.
2. 내 **그룹에 대한 쇼핑 을 선택합니다.**
3. 검색을 사용하여 원하는 앱을 찾고 앱을 선택합니다.
4. 제품 세부 정보에서 앱 **다운로드를 선택합니다.** Microsoft Store 앱을 조직의 **제품에** 추가합니다.

**Intune과 Intune 간에 동기화를 비즈니스용 Microsoft Store**
1. Microsoft Endpoint Manager [센터에 로그인합니다.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. **테넌트 관리**  >  **커넥터 및 토큰을 비즈니스용 Microsoft Store.**  >  
3. **동기화를** 선택하여 앱에서 구입한 앱을 Intune으로 Microsoft Store 선택합니다.

**Intune과 Intune 간의 동기화가 비즈니스용 Microsoft Store 확인**
1. 비즈니스용 Microsoft Store 관리자 [계정으로](https://businessstore.microsoft.com) 비즈니스용 Microsoft Store 로그인합니다.
2. 관리를 **선택합니다.**
3. 를 **설정** 를 선택한 다음 **배포를 선택합니다.**
4. 관리 **도구에서** Intune이 나열되어 있으며 상태가 활성 상태인지 **확인**  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>2단계: Azure AD 그룹 만들기

각 앱에 대해 3개의 Azure AD 그룹을 생성합니다. 이 표에서는 필요한 그룹(사용 가능, 필수 및 제거)에 대해 간략하게 설명합니다. 

앱 할당 유형 |    그룹 사용    | 예제 Azure AD 이름
--- | --- | ---
사용 가능 |  앱은 앱 또는 웹 사이트에서 회사 포털 있습니다. | MMD – *앱 이름* - 사용 가능
필수 |  앱이 선택한 그룹의 장치에 설치됩니다. | MMD – *앱 이름* - 필수
제거 |  선택한 그룹의 장치에서 앱이 제거됩니다. | MMD – *앱 이름* – 제거

이러한 그룹에 사용자를 추가하여 앱을 사용할 수 있도록 설정하거나, 앱을 설치하거나, 앱의 디바이스에서 앱을 Microsoft Managed Desktop 있습니다. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>3단계: 사용자에게 앱 할당

**사용자에게 앱을 할당하기 위해**

1. 관리자 포털 [Microsoft Managed Desktop 로그인합니다.](https://aka.ms/mmdportal)
2. 관리되는 데스크톱 창에서 앱을 **선택합니다.**
3. 앱 작업 부하에서 사용자를 할당할 앱을 선택하고 사용자 그룹 **할당을 선택합니다.**
4. 특정 앱에 대해 할당 유형(사용 가능, 필수, 제거)을 선택하고 적절한 그룹을 할당합니다.
5. 앱 할당 창에서 확인 을 **선택합니다.**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털](access-admin-portal.md)에 액세스합니다.
1. [관리 포털의 관리자 연락처를 추가하고 확인합니다](add-admin-contacts.md).
1. [등록 후 설정을 조정합니다](conditional-access.md).
1. [Intune 회사 포털](company-portal.md)을 배포하고 할당합니다.
1. [라이선스를 할당합니다](assign-licenses.md).
1. 앱 배포(이 문서).
1. [디바이스를 설정합니다](set-up-devices.md).
1. [Autopilot 및 등록 상태 페이지의 첫 실행 환경](esp-first-run.md)을 설정합니다.
1. [사용자 지원 기능을 사용하도록 설정합니다](enable-support.md).
1. [사용자가 디바이스를 사용할 수 있도록 준비합니다](get-started-devices.md).
1. [앱 컨트롤을 시작합니다](get-started-app-control.md).


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->