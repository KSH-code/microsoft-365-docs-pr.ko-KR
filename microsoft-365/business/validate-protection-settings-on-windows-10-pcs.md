---
title: Windows 10 PC에서 앱 보호 설정 유효성 검사
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Windows 10 장치에서 Microsoft 365 Business 앱 보호 설정을 확인 하 고 사용자가 회사 데이터를 개인 파일이 나 관리 되지 않는 앱에 복사할 수 없는지 확인 합니다.
ms.openlocfilehash: 4d3d7e950311ac32606e700ebb35bf026ae091cc
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550000"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Windows 10 PC에서 앱 보호 설정 유효성 검사

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>사용자가 회사 장치의 개인 파일에 회사 데이터를 복사할 수 없는지 확인합니다.

[앱 보호 정책을 설정한](protection-settings-for-windows-10-devices.md)후에는 정책이 사용자 장치에 적용 되는 데 몇 시간이 걸릴 수 있습니다. **사용자가 회사 데이터를 개인 파일로 복사 하지 않도록** 설정 하 고 회사 소유의 장치에 대 한 비즈니스용 OneDrive 설정에 작업을 강제로 저장 하 **는 경우에는 사용자** 의 장치에서 Azure AD에 연결 하 여 로그인 한 후에이를 확인할 수 있습니다. 
  
 **연결 설정 확인**
  
1. [Microsoft 365 Business 사용자를 위한 Windows 장치 설정](set-up-windows-devices.md) 에 설명된 것처럼 Microsoft 365 Business 자격 증명으로 로그인하고 Azure AD에 연결한 후 **Windows 설정** \> **계정** \> **회사 또는 학교 액세스**로 이동합니다. **\<테넌트 이름\> Azure AD에 연결됨**을 선택한 다음 **정보**를 선택합니다.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. 테 \<넌 트\> 이름 **으로 관리** 페이지에서 다음 그림에 표시 된 것과 같은 **관리 서버 주소** 를 포함 하는 **연결 정보** 를 볼 수 있습니다. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **관리 되지 않는 앱에 회사 데이터를 붙여넣을 수 없는지 확인**
  
1. Microsoft 365 Business가 설치한 Outlook 2016을 엽니다.
    
2. 전자 메일을 열고 전자 메일의 일부 콘텐츠를 복사합니다.
    
    메모장을 열고 콘텐츠 붙여넣기를 시도합니다.
    
    앱에서 콘텐츠에 액세스할 수 없다는 오류 메시지가 표시 됩니다.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    하지만 Word 2016에는 동일한 콘텐츠를 붙여넣을 수 있습니다.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>사용자가 개인 장치의 개인 파일에 회사 데이터를 복사할 수 없는지 확인합니다.

 **연결 설정 확인**
  
1. 로컬 사용자로 로그인 한 windows 10 개인 디바이스에서 **windows 설정**으로 이동 하 고 **계정** \> **액세스 회사 또는 학교**를 클릭 하거나 탭 합니다.
    
2. **회사 또는 학교 액세스**에서 **연결**을 선택합니다.
    
3. Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.
    
4. **회사 또는 학교 액세스** 페이지에서 **회사 또는 학교 계정**을 선택한 다음 **정보**를 선택합니다.
    
    ![회사 또는 학교 계정 대화 상자에서 정보를 클릭 하거나 탭 합니다.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. **액세스 회사 또는 학교** 페이지에서 다음 그림에 표시 된 것과 같은 **관리 서버 주소** 를 포함 하는 **연결 정보** 를 볼 수 있으며,에는 *wip* 및 *mam* 이라는 단어가 포함 됩니다. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **관리 되지 않는 앱에 회사 데이터를 붙여넣을 수 없는지 확인**
  
1. Outlook 2016을 열고 필요한 경우 Microsoft 365 Business 계정을 추가하고 Microsoft 365 Business 자격 증명으로 로그인합니다.
    
2. 전자 메일을 열고 전자 메일의 일부 콘텐츠를 복사합니다.
    
    메모장을 열고 콘텐츠 붙여넣기를 시도합니다.
    
    앱에서 콘텐츠에 액세스할 수 없다는 오류가 표시 됩니다.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    하지만 Word 2016에는 동일한 콘텐츠를 붙여넣을 수 있습니다.
    

