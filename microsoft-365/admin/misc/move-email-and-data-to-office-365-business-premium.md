---
title: Office 365 Business Premium으로 전자 메일 및 데이터 이동
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: 새 비즈니스 id로 데이터를 이동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 878d4b66907cc6419ff23cbb61e56e32c7c601bc
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257298"
---
# <a name="move-email-and-data-to-office-365-business-premium"></a>Office 365 Business Premium으로 전자 메일 및 데이터 이동

Office 365 Business Premium으로 업그레이드 하면 새로운 *비즈니스 id*가 제공 됩니다. 새로운 전자 메일 계정과 비즈니스 데이터에 대한 별도의 OneDrive 계정을 얻습니다. 
  
일부 개인 데이터를 새 비즈니스 ID로 이동하려면 경우 아래 지침을 따르세요.
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **OneDrive 데이터 복사**
1. 비즈니스용 Office 365로 마이그레이션하려는 파일을 일시적으로 저장할 임시 폴더를 하드 드라이브에 만듭니다.
    
2. 으로 이동 [https://onedrive.live.com/](https://onedrive.live.com/) 하 고 Home 구독의 Office 365에 액세스 하는 데 사용 하는 Microsoft 계정을 사용 하 여 로그인 합니다. 
    
3. 비즈니스용 Office 365에서 사용하려는 파일을 1단계에서 만든 로컬 폴더로 복사합니다.
    
 **OneDrive 파일을 비즈니스용 Office 365로 가져오기**
1. [Admin.microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877) 으로 이동 하 여 Office 365 Business 사용자 이름 및 암호를 사용 하 여 로그인 합니다. 
    
2. 왼쪽 위에서 **앱 시작 관리자** 아이콘을 선택한 다음 **OneDrive**를 선택합니다.
  
    > [!TIP]
    > 비즈니스용 OneDrive를 처음으로 열 때 OneDrive를 설정해야 합니다. 이 경우 **비즈니스용 OneDrive 시작** 페이지에서 **다음**을 선택 합니다. OneDrive가 설정 된 후 **onedrive가 준비 됨**을 선택 합니다. 
  
3. 빈 OneDrive 폴더로 이동합니다. 하위 폴더를 만들려면 **새** \> **폴더**를 선택 합니다.

4. **업로드** 를 선택 하 여 OneDrive 파일을 복사한 하드 드라이브의 파일을 복사 합니다. 
  
    > [!NOTE]
    >  개별 파일 및 파일 그룹(예: 특정 폴더의 모든 파일)을 한 번에 업로드할 수 있지만 비즈니스용 OneDrive로 폴더를 복사할 수는 없습니다. 대신, 비즈니스용 OneDrive에 원하는 폴더 구조를 만들어야 합니다. >  4단계에서 만든 폴더로 파일을 복사하려는 경우 파일을 업로드하기 전에 해당 폴더를 엽니다. 그렇지 않은 경우 파일이 루트 폴더에 업로드됩니다. 파일을 업로드한 후 비즈니스용 OneDrive의 폴더 간에 파일을 이동할 수도 있습니다. 
  
## <a name="outlookemail"></a>[Outlook/전자 메일](#tab/Outlook)
  
 **Outlook 데이터 파일로 Outlook 2013 정보 내보내기**
1. Outlook 데이터 파일(.pst)을 만들려면 먼저 Outlook 정보를 내보낼 계정이 이미 데스크톱 버전의 Outlook에 추가되어 있어야 합니다. Outlook 2013 이상에 계정을 추가하는 방법에 대한 내용은 [(Windows용) Outlook에서 전자 메일 설정](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) 또는 [Outlook for Mac 2011에서 전자 메일 설정](https://support.office.com/article/d7b404a0-6e18-4d95-bed8-2de7661563ca.aspx)을 참조하세요.
    
2. 각 사용자는 [전자 메일, 연락처 및 일정을 Outlook .pst 파일로 내보내기 또는 백업](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)의 단계를 완료해야 합니다.
    
 **Outlook에서 새 전자 메일 계정 설정**
1. 각 사용자는 비즈니스용 Office 365 구독과 함께 제공되는 새 전자 메일 계정을 설정해야 합니다. 이렇게 하려면 새 전자 메일 계정의 주소가 필요합니다. 각 사용자의 전자 메일 계정은 비즈니스용 Office 365에 로그인하는 데 사용하는 사용자 이름과 같습니다. 예를 들면 sue@contoso.onmicrosoft.com 또는 david@contoso.com과 비슷합니다.
    
2. 전자 메일 계정을 Outlook에 추가하도록 각 사용자에게 요청하세요. 자세한 내용은 [(Windows용) Outlook에서 전자 메일 설정](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) 또는 [Outlook for Mac 2011에서 전자 메일 설정](https://support.office.com/article/d7b404a0-6e18-4d95-bed8-2de7661563ca.aspx)을 참조하세요.
    
 **Outlook 데이터 파일에서 정보 가져오기**
1. 그러면 PST 파일에 저장된 전자 메일, 일정, 작업 및 연락처가 비즈니스용 Office 365 전자 메일 계정으로 병합됩니다.
    
2. PST 파일에 저장된 정보를 비즈니스용 Office 365 전자 메일 계정으로 가져오려면 각 사용자가 [Outlook.pst 파일에서 전자 메일, 연락처 및 일정 가져오기](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac.aspx)의 단계를 완료하도록 하세요.
    
---

