---
title: 삭제된 Office 365 그룹 복원
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Exchange 관리 센터를 사용 하 여 삭제 된 Office 365 그룹을 복원 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 98eb00d90f5b607a58cd32728ce43cb4a1de1ff5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246558"
---
# <a name="restore-a-deleted-office-365-group"></a>삭제된 Office 365 그룹 복원

Office 365 그룹의 소유자 인 경우 다음 단계를 수행 하 여 직접 그룹을 복원할 수 있습니다.

1. 삭제 된 [그룹 페이지](https://outlook.office.com/people/group/deleted)에서 **그룹** 노드 아래의 **그룹 관리** 옵션을 선택한 다음 **삭제**를 선택 합니다.
2. 복원 하려는 그룹 옆에 있는 **복원** 탭을 클릭 합니다.

삭제 된 그룹이 여기에 표시 되지 않으면 관리자에 게 문의 하십시오.
  
Office 365 그룹을 복원 하려는 사용자 인 경우 관리자에 게 이러한 단계를 수행 하도록 요청 하거나 지원 센터에 문의 하세요.  
   
그룹을 삭제 한 경우에는 기본적으로 30 일간 보존 됩니다. 이 30 일의 기간은 여전히 그룹을 복원할 수 있기 때문에 "일시 삭제"로 간주 됩니다. 30 일이 지나면 그룹 및 관련 내용이 영구적으로 삭제 되며 복원할 수 없습니다.
  
"일시 삭제" 기간 동안 사용자가 사이트에 액세스 하려고 하면 404 _금지_ 된 메시지가 표시 됩니다. 이 기간 후 사용자가 사이트에 액세스 하려고 하면 404 _찾을 수 없음_ 메시지가 표시 됩니다.
  
그룹이 복원되면 다음 콘텐츠가 복원됩니다.
  
- Azure AD (Active Directory) Office 365 그룹 개체, 속성 및 구성원
    
- 그룹의 전자 메일 주소입니다.
    
- Exchange Online 공유 받은 편지함 및 일정
    
- SharePoint Online 팀 사이트 및 파일
    
- OneNote 전자 필기장
    
- Planner
    
- Teams

- Yammer 그룹 및 그룹 콘텐츠 (Yammer에서 Office 365 그룹을 만든 경우)
    
콘텐츠가 영구적으로 삭제되도록 보존 기간 30일을 기다릴 수 없는 경우 [Office 365그룹 영구적으로 삭제](#permanently-delete-an-office-365-group)할 수도 있습니다. 

> [!NOTE]
> 삭제 된 Office 365 그룹의 소유자도 그룹을 복원할 수 있습니다. 관리자 권한 없이 소유자 권한을 사용 하 여 office 365 그룹을 복원 하려면 [PowerShell을 사용 하 여 office 365 그룹 복원을](#restore-an-office-365-group-using-powershell)참조 하십시오.

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a>Exchange 관리 센터를 사용하여 Office 365 그룹 복원

Office 365 전역 관리자 권한이 있어야 합니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a> 로 이동합니다.
    
2. Exchange 관리 센터에서 **받는 사람**을 선택한 다음 **그룹**을 선택합니다. 그룹이 활성 상태 인지 일시 삭제 되었는지 확인할 수 있습니다. 그룹이 영구적으로 삭제된 경우에는 목록에 표시되지 않습니다.
  
3. 그룹이 일시 삭제 된 정확한 시간을 보려면 그룹을 선택 하 고 오른쪽 창에서 정보를 확인 합니다.
      
4. 복원할 그룹을 선택한 다음 복원 아이콘을 선택 합니다.
    
    ![복원할 그룹을 선택한 다음 복원 아이콘을 선택 합니다.](../media/restore-group.png)
  
5. 새로 고침 선택 ![새로 고침 아이콘](../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) 을 선택합니다. 그룹이 활성으로 표시됩니다. 그룹과 연결 된 양식 및 양식 데이터도 복원 됩니다.
    
## <a name="restore-an-office-365-group-using-powershell"></a>PowerShell을 사용하여 Office 365그룹 복원

Office 365 전역 관리자 권한이 있거나 삭제 된 Office 365 그룹의 이전 소유자 여야 합니다.

> [!IMPORTANT]
> PowerShell에서 Remove-msolgroup을 사용 하 여 그룹을 삭제 하는 경우 그룹이 영구적으로 삭제 됩니다. PowerShell을 사용하여 그룹을 삭제하는 경우 **Remove-AzureADMSGroup**을 사용하여 Office 365 그룹을 일시 삭제하는 것이 좋습니다. 이렇게 해야 필요한 경우 복원할 수 있습니다. 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a>Azure Active Directory PowerShell for Graph의 미리 보기 버전 설치

> [!IMPORTANT]
> 같은 컴퓨터에 preview와 GA 버전을 동시에 모두 설치할 수는 없습니다.
  
최상의 방법으로는 이전 AzureADPreview 또는 이전 AzureAD 버전을 제거 하 여 *항상* 최신 상태로 유지 하는 것이 좋습니다. 
  
 
1. 검색 창에 Windows PowerShell을 입력합니다.
    
2. Right-click on **Windows PowerShell** and select **Run as Administrator**.
  
2. 설치 된 모듈을 검토 합니다.
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. 이전 버전의 AzureADPreview 또는 AzureAD를 제거하려면 다음 명령을 실행합니다.
  
```
   Uninstall-Module AzureADPreview
```

또는
  
```
   Uninstall-Module AzureAD
```

4. To install the latest version of AzureADPreview, run this command:
  
```
   Install-Module AzureADPreview
```



At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. 
  
### <a name="restore-the-deleted-group"></a>삭제된 그룹 복원
  
1. Previoius 섹션의 "Windows PowerShell 용 Azure Active Directory 모듈의 preview 버전 설치"에 설명 된 대로 **AzureADPreview** 모듈을 설치 했습니까?  위 단계가 작동하지 않는 가장 흔한 이유는 바로 최신 버전의 **미리 보기** 가 설치되어 있지 않은 것입니다. 
    
2. 컴퓨터에서 Windows PowerShell 창을 엽니다(일반적인 Windows PowerShell 창이든 **관리자 권한으로 실행**을 선택하여 연 창이든 관계없습니다).
    
3. 다음 명령을 실행 하 여 각 명령 다음에 **enter** 키를 누릅니다. 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  열리는 **계정에 로그인** 화면에서 관리자 계정 사용자 이름 및 암호를 입력 하 여 Azure AD 서비스에 연결 하 고 **로그인**을 선택 합니다.
  
4. 다음 명령을 실행 하 여 조직의 일시 삭제 된 모든 Office 365 그룹을 30 일 동안 계속 해 서 표시 합니다.
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. 복원하려는 그룹(하나 또는 여러 개)의 개체 ID를 기록해 둡니다. 이 목록에 찾으려는 그룹이 표시 되지 않으면 해당 그룹은 이미 영구적으로 제거 된 것일 수 있습니다.
    
    > [!CAUTION]
    > 삭제된 그룹과 같은 별칭 또는 SMTP 주소로 새 그룹이 만들어진 경우 삭제된 그룹을 복원할 수 있으려면 먼저 해당 새 그룹을 삭제해야 합니다. 
  
6. 해당 그룹을 복원 하려면 다음 명령을 실행 합니다.
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. 일반적으로이 프로세스는 몇 분 정도 걸리지만 몇 가지 드문 경우에도 완전히 복원 하는 데 24 시간이 걸릴 수 있습니다. 그룹이 복원되었는지 확인하려면 PowerShell에서 이 명령을 실행합니다.
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

복원이 완료되고 나면 그룹이 Outlook 및 웹용 Outlook의 탐색 창에 다시 나타나야 합니다. 그룹 구성원이 SharePoint 및 Planner를 비롯한 복원된 모든 콘텐츠를 다시 사용할 수 있어야 합니다.
  
## <a name="permanently-delete-an-office-365-group"></a>Office 365그룹 영구적으로 삭제

경우에 따라 30 일 일시 삭제 기간이 만료 될 때까지 기다리지 않고 그룹을 영구적으로 제거할 수 있습니다. 이렇게 하려면 PowerShell을 시작하고 이 명령을 실행하여 그룹의 개체 ID를 가져옵니다.
  
```
Get-AzureADMSDeletedGroup
```

영구적으로 삭제 하려는 그룹 (또는 그룹)의 개체 ID를 기록해 둡니다.
  
> [!CAUTION]
> 그룹을 제거하면 그룹 및 해당 데이터가 영구적으로 제거됩니다. 
  
그룹을 제거하려면 PowerShell에서 이 명령을 실행합니다.
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

그룹이 제거되었는지 확인하려면  *Get-AzureADMSDeletedGroup*  cmdlet을 다시 실행하여 그룹이 소프트 삭제된 그룹 목록에 더 이상 나타나지 않는지 확인합니다. 일부 경우 그룹 및 모든 해당 데이터가 영구적으로 삭제되는 데 24시간이 걸릴 수도 있습니다. 
  
## <a name="got-questions-about-office-365-groups"></a>Office 365 그룹에 대한 질문이 있나요?

[Microsoft 기술 커뮤니티](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 를 방문 하 여 질문을 게시 하 고 Office 365 그룹에 대 한 대화에 참여 하세요. 
  
## <a name="related-articles"></a>관련 문서

[PowerShell을 사용하여 Office 365 그룹 관리](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Remove-UnifiedGroup cmdlet을 사용하여 그룹 삭제](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[그룹에 연결된 팀 사이트 설정 관리](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Outlook에서 그룹 삭제](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
