---
title: Microsoft 365 Business Standard로 전자 메일 및 데이터 이동
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: 데이터를 새 비즈니스 ID로 이동하는 방법을 배워야 합니다.
ms.openlocfilehash: 4f105e00ab6496a5d1d3edfc0e0f1abd4eced412
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645038"
---
# <a name="move-email-and-data-to-microsoft-365-business-standard"></a>Microsoft 365 Business Standard로 전자 메일 및 데이터 이동

Microsoft 365 Business Standard로 업그레이드하면 새로운 비즈니스 ID가 *제공됩니다.* 새로운 전자 메일 계정과 비즈니스 데이터에 대한 별도의 OneDrive 계정을 얻습니다. 
  
일부 개인 데이터를 새 비즈니스 ID로 이동하려면 경우 아래 지침을 따르세요.
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **OneDrive 데이터 복사**
1. 영구 드라이브에 임시 폴더를 만들어 비즈니스용 Microsoft 365로 마이그레이션하려는 파일을 임시로 저장합니다.
    
2. Go to [https://onedrive.live.com/](https://onedrive.live.com/) and sign in using the Microsoft account that you use to access your Microsoft 365 Family subscription. 
    
3. 비즈니스용 Microsoft 365에서 사용할 파일을 1단계에서 만든 로컬 폴더에 복사합니다.
    
 **비즈니스용 Microsoft 365로 OneDrive 파일 가져오기**
1. Go to [admin.microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877) and sign in with your Microsoft 365 Apps for business user name and password. 
    
2. 왼쪽 위에서 **앱 시작 관리자** 아이콘을 선택한 다음 **OneDrive** 를 선택합니다.
  
    > [!TIP]
    > 비즈니스용 OneDrive를 처음으로 열 때 OneDrive를 설정해야 합니다. 이 경우 비즈니스용 **OneDrive** 시작 페이지에서 다음을 **선택합니다.** OneDrive를 설정한 후 **OneDrive를 선택할 수 있습니다.** 
  
3. 빈 OneDrive 폴더로 이동합니다. 하위 폴더를 만들하려면 새 **폴더를** \> **선택합니다.**

4. OneDrive 파일을 복사한 하드 드라이브에서 파일을 복사하려면 업로드를 선택합니다.  
  
    > [!NOTE]
    >  개별 파일 및 파일 그룹(예: 특정 폴더의 모든 파일)을 한 번에 업로드할 수 있지만 비즈니스용 OneDrive로 폴더를 복사할 수는 없습니다. 대신, 비즈니스용 OneDrive에 원하는 폴더 구조를 만들어야 합니다. >  4단계에서 만든 폴더로 파일을 복사하려는 경우 파일을 업로드하기 전에 해당 폴더를 엽니다. 그렇지 않은 경우 파일이 루트 폴더에 업로드됩니다. 파일을 업로드한 후 비즈니스용 OneDrive의 폴더 간에 파일을 이동할 수도 있습니다. 
  
## <a name="outlookemail"></a>[Outlook/전자 메일](#tab/Outlook)
  
 **Outlook 데이터 파일로 Outlook 2013 정보 내보내기**
1. Outlook 데이터 파일(.pst)을 만들려면 먼저 Outlook 정보를 내보낼 계정이 이미 데스크톱 버전의 Outlook에 추가되어 있어야 합니다. Outlook 2013 이상에 계정을 추가하는 방법에 대한 내용은 [(Windows용) Outlook에서 전자 메일 설정](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) 또는 [Outlook for Mac 2011에서 전자 메일 설정](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54)을 참조하세요.
    
2. 각 사용자는 [전자 메일, 연락처 및 일정을 Outlook .pst 파일로 내보내기 또는 백업](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)의 단계를 완료해야 합니다.
    
 **Outlook에서 새 전자 메일 계정 설정**
1. 각 사용자는 비즈니스용 Microsoft 365 구독과 함께 제공된 새 전자 메일 계정을 설정해야 합니다. 이렇게 하려면 새 전자 메일 계정의 주소가 필요합니다. 각 사용자의 전자 메일 계정은 비즈니스용 Microsoft 365에 로그인하는 데 사용하는 사용자 이름과 동일합니다. 예를 들면 sue@contoso.onmicrosoft.com 또는 david@contoso.com과 비슷합니다.
    
2. 전자 메일 계정을 Outlook에 추가하도록 각 사용자에게 요청하세요. 자세한 내용은 [(Windows용) Outlook에서 전자 메일 설정](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) 또는 [Outlook for Mac 2011에서 전자 메일 설정](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54)을 참조하세요.
    
 **Outlook 데이터 파일에서 정보 가져오기**
1. 그러면 PST 파일에 저장된 전자 메일, 일정, 작업 및 연락처가 비즈니스용 Microsoft 365 전자 메일 계정으로 병합됩니다.
    
2. PST 파일에 저장된 정보를 비즈니스용 Microsoft 365 전자 메일 계정으로 가져오기하려면 각 사용자가 Outlook .pst 파일에서 전자 메일, 연락처 및 일정 가져오기 단계를 [완료하도록 합니다.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
    
---

