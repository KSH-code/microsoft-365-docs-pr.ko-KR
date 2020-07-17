---
title: 관리 센터에서 추가 기능 관리
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
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 관리 센터에서 중앙 집중식 배포를 사용 하 여 조직의 사용자 및 그룹에 추가 기능을 배포 하는 방법을 알아봅니다.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103114"
---
# <a name="manage-add-ins-in-the-admin-center"></a>관리 센터에서 추가 기능 관리

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

Office 추가 기능은 문서를 개인 설정 하 고 웹에서 정보에 액세스 하는 방법을 간소화 하는 데 도움이 됩니다 ( [Office 추가 기능 사용 시작](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)참조). 

관리자가 조직의 사용자에 대 한 추가 기능을 배포한 후에는 관리자가 추가 기능을 해제 하거나 설정, 편집, 삭제 및 관리 하 여 추가 기능에 대 한 액세스를 관리할 수 있습니다.

관리 센터에서 추가 기능을 설치 하는 방법에 대 한 자세한 내용은 [관리 센터에서 추가 기능 배포](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)를 참조 하세요.
  
## <a name="add-in-states"></a>추가 기능 상태

추가 기능의 **설정** 또는 **해제** 상태 중 하나를 사용할 수 있습니다.
  
|**상태**|**상태가 적용되는 경우**|**영향**|
|:-----|:-----|:-----|
|**활성**  <br/> |관리자가 추가 기능을 업로드 하 고 사용자 또는 그룹에 할당 했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹은 관련 클라이언트에서 추가 기능을 볼 수 있습니다.  <br/> |
|**해제됨**  <br/> |관리자가 추가 기능을 해제했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.  <br/> 추가 기능 상태가 활성으로 변경되면 사용자 및 그룹이 추가 기능에 다시 액세스할 수 있습니다.  <br/> |
|**삭제됨**  <br/> |관리자가 추가 기능을 삭제했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.  <br/> |
   
더 이상 사용 하지 않는 추가 기능을 삭제 하는 것이 좋습니다. 예를 들어 추가 기능을 해제 하는 작업은 특정 기간 동안에만 사용 되는 경우에 적합할 수 있습니다.

## <a name="delete-an-add-in"></a>추가 기능 삭제

배포 된 추가 기능을 삭제할 수도 있습니다.

1. 관리 센터에서 **설정**  >  **서비스 & 추가** 기능 페이지로 이동 합니다.

2. 배포 된 추가 기능을 선택 합니다.

3. **추가 기능 삭제**를 클릭 합니다. 오른쪽 아래 모서리에 있는 추가 기능 단추를 제거 합니다.

4. 선택한 항목의 유효성을 검사 하 고 **추가 기능 제거**를 선택 합니다.

## <a name="edit-add-in-access"></a>추가 기능 액세스 편집

배포 후 관리자는 추가 기능에 대 한 사용자 액세스를 관리할 수도 있습니다.

1. 관리 센터에서 **설정**  >  **서비스 & 추가** 기능 페이지로 이동 합니다.

2. 배포 된 추가 기능을 선택 합니다.

3. **액세스 권한이 있는 사용자**아래에서 **편집** 을 클릭 합니다.

4. 변경 내용을 저장 합니다.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>모든 클라이언트로부터 Office 스토어를 꺼서 추가 기능 다운로드 방지 (Outlook 제외)

> [!NOTE]
> Outlook 추가 기능 설치는 [다른 프로세스](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)를 통해 관리 됩니다.

조직에서는 Office 스토어에서 새 Office 추가 기능을 다운로드 하지 못하도록 할 수 있습니다. 이를 중앙 집중식 배포와 함께 사용 하 여 조직 내에서 사용자에 게 승인 된 추가 기능만 배포 되도록 할 수 있습니다.
  
**추가 기능 취득 기능을 해제 하려면**
  
1. 관리 센터 미리 보기에서 **설정** \> [서비스 &amp; 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=2053743) 페이지로 이동합니다.
    
3. **사용자가 소유한 앱 및 서비스를**선택 합니다.
    
4. 사용자가 Office 스토어에 액세스 하도록 허용 하는 옵션을 선택 취소 합니다.

이렇게 하면 모든 사용자가 저장소에서 다음 추가 기능을 취득할 수 없습니다.
  
- Word, Excel 및 PowerPoint 2016의 추가 기능:
    
  - Windows
    
  - Mac
    
  - 사무실
    
    
- **Appsource** 내에서 시작 하는 인수
    
- Microsoft 365 내의 추가 기능
    
저장소에 액세스 하려고 하는 사용자에 게는 **Office 스토어 추가 기능의 개별 가져오기를 차단 하도록 Microsoft 365이 구성 되어** 있습니다.
  
다음 버전에서는 Office 스토어의 기능 지원을 사용할 수 있습니다.
  
- Windows: 16.0.9001-현재 사용 가능 합니다.
    
- Mac: 16.10.18011401-현재 사용 가능 합니다.
    
- iOS: 2.9.18010804-현재 사용 가능 합니다.
    
- 웹-현재 사용 가능 합니다.
    
이는 관리자가 중앙 집중식 배포를 사용 하 여 Office 스토어에서 추가 기능을 할당 하는 것을 막지는 못합니다.
  
사용자가 Microsoft 계정으로 로그인 하지 못하게 하기 위해 조직 계정만 사용 하도록 로그온을 제한할 수 있습니다. 자세한 내용은 [Office 2016의 id, 인증 및 권한 부여](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)를 참조 하세요.  

## <a name="more-about-the-end-user-experience-with-add-ins"></a>추가 기능의 최종 사용자 환경에 대 한 추가 정보

추가 기능을 배포한 후에는 최종 사용자가 Office 응용 프로그램에서 사용을 시작할 수 있습니다 ( [Office 추가 기능 사용 시작](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)참조). 추가 기능에서 지 원하는 모든 플랫폼에 추가 기능이 표시 됩니다.
  
추가 기능이 추가 기능 명령을 지원하는 경우 명령은 Office 리본에 나타납니다. 다음 예에서는 **인용 검색** 명령이 **인용** 추가 기능에 나타납니다. 

![검색 인용이 있는 Office 리본 메뉴](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
배포 된 추가 기능이 추가 기능 명령을 지원 하지 않거나 배포한 모든 추가 기능을 보려는 경우 **내 추가 기능**을 통해 볼 수 있습니다. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016, Excel 2016 또는 PowerPoint 2016의 경우

1. ** \> 내 추가 기능 삽입을**선택 합니다. 
    
2. Office 추가 기능 창에서 **관리자가 관리함** 탭을 선택합니다. 
    
3. 이전에 배포한 추가 기능을 두 번 클릭합니다(이 예에서는 **인용** ). <br/>![Office 추가 기능 페이지의 관리 관리 탭](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook의 경우

1. **홈** 리본에서 **추가 기능 가져오기를**선택 합니다.<br/>![Outlook의 스토어 단추](../../media/getaddinsicon.png)
  
2. 왼쪽 탐색 창에서 **관리-관리** 를 선택 합니다. 

## <a name="learn-more"></a>자세한 정보

[관리 센터에 추가 기능 배포](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Office 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=846362)을 만들고 빌드하는 방법에 대해 자세히 알아보세요.
  
[중앙 집중식 배포 PowerShell cmdlet을 사용 하 여 추가 기능을 관리](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)합니다.
  
[문제 해결: 사용자가 추가 기능을 볼 수 없음](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Microsoft 스토어에서 추가 기능 미성년자가 및 가져오기](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)