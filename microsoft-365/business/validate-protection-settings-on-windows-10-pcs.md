---
title: Windows 10 PC에서 앱 보호 설정 유효성 검사
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Windows 10 장치에서 Microsoft 365 Business Premium 앱 보호 설정의 유효성을 검사하고 사용자가 회사 데이터를 개인 파일 또는 관리되지 않는 앱에 복사할 수 없는지 확인합니다.
ms.openlocfilehash: e319ffa5149f055b5de45078facc8899acffc223
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579865"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Windows 10 PC에서 앱 보호 설정 유효성 검사

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>사용자가 회사 장치의 개인 파일에 회사 데이터를 복사할 수 없는지 확인합니다.

앱 [보호](protection-settings-for-windows-10-devices.md)정책을 설정한 후 정책이 사용자의 장치에 적용되는 데 최대 몇 시간이 걸릴 수 있습니다. 사용자가 회사  데이터를 개인 파일에 복사할 수 없습니다.를 으로 설정하고 회사 소유 장치에 대한 비즈니스용 **OneDrive에** 회사 파일을 저장하도록 강제 설정한 경우 Azure AD에 연결하고 로그인한 후 사용자의 장치에서 이 설정을 확인할 수 있습니다. 
  
 **연결 설정 확인**
  
1. Microsoft 365 Business Premium 자격 증명으로 로그인하고 [Microsoft 365 Business Premium](set-up-windows-devices.md)사용자를 위한 Windows 장치 설정에 설명된 바와 같이 Azure AD에 연결한 후 **Windows** 설정 계정 직장 또는 학교 액세스로 \>  \> **이동합니다.** **\<tenant name\> Azure AD에 연결 을 선택한** 다음 정보 **를 선택 합니다.**
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. 관리되는 **사용자 페이지에서** 다음 그림과 같이 관리 서버 주소를 포함하는 연결 정보를 볼 수 \<tenant name\> 있습니다.   
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **관리되지 않는 앱에 회사 데이터를 붙여넣을 수 없는지 확인**
  
1. Microsoft 365 Business Premium에서 설치한 Outlook 2016을 열 수 있습니다.
    
2. 전자 메일을 열고 전자 메일의 일부 콘텐츠를 복사합니다.
    
    메모장을 열고 콘텐츠 붙여넣기를 시도합니다.
    
    앱이 콘텐츠에 액세스할 수 없다고 하는 오류가 표시됩니다.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    하지만 Word 2016에는 동일한 콘텐츠를 붙여넣을 수 있습니다.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>사용자가 개인 장치의 개인 파일에 회사 데이터를 복사할 수 없는지 확인합니다.

 **연결 설정 확인**
  
1. 로컬 사용자로 로그인한 Windows 10 개인 장치에서 **Windows** 설정으로 이동하여 계정 액세스  직장 또는 학교 를 클릭하거나 \> **탭합니다.**
    
2. **회사 또는 학교 액세스** 에서 **연결** 을 선택합니다.
    
3. Microsoft 365 Business Premium 자격  증명을 직장 또는 학교 계정 설정 대화 상자 로그인 에 \> **입력합니다.**
    
4. **회사 또는 학교 액세스** 페이지에서 **회사 또는 학교 계정** 을 선택한 다음 **정보** 를 선택합니다.
    
    ![직장 또는 학교 계정 대화 상자에서 정보를 클릭하거나 탭합니다.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. 직장 **또는** 학교 액세스 페이지에서 다음  그림에 표시된  주소와 같은 관리 서버 주소를 포함하는 연결 정보를 볼 수 있으며, *여기에는 wip* 및 *mam* 단어가 포함됩니다. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **관리되지 않는 앱에 회사 데이터를 붙여넣을 수 없는지 확인**
  
1. Outlook 2016을 열고 필요한 경우 Microsoft 365 Business Premium 계정을 추가하고 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.
    
2. 전자 메일을 열고 전자 메일의 일부 콘텐츠를 복사합니다.
    
    메모장을 열고 콘텐츠 붙여넣기를 시도합니다.
    
    앱이 콘텐츠에 액세스할 수 없다고 하는 오류가 표시됩니다.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    하지만 Word 2016에는 동일한 콘텐츠를 붙여넣을 수 있습니다.
    

