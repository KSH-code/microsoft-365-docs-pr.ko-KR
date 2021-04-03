---
title: 관리 센터에서 추가 기능 관리
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 중앙 집중식 추가 기능을 사용하여 조직의 사용자 및 그룹에 추가 기능을 배포하는 방법을 학습합니다.
ms.openlocfilehash: 8503ed7ea2e088a8e17b52e619ee999aa05f497a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579293"
---
# <a name="manage-add-ins-in-the-admin-center"></a>관리 센터에서 추가 기능 관리

Office 추가 기능을 사용하면 문서를 개인 설정하고 웹의 정보에 액세스하는 방법을 간소화할 수 있습니다(Office 추가 기능 사용 시작 [참조).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 

관리자가 조직의 사용자에 대해 추가 기능을 배포한 후 추가 기능을 해제하거나 설정하고, 추가 기능 액세스 권한을 편집, 삭제 및 관리할 수 있습니다.

관리 센터에서 추가 기능을 설치하는 데 대한 자세한 내용은 관리 센터에서 추가 기능 [배포를 참조하세요.](./manage-deployment-of-add-ins.md)
  
## <a name="add-in-states"></a>추가 기능 상태

추가 기능의 상태는 **On** 또는 **Off 상태일 수** 있습니다.
  
|**상태**|**상태가 적용되는 경우**|**영향**|
|:-----|:-----|:-----|
|**활성**  <br/> |관리자가 추가 기능을 업로드하고 사용자 또는 그룹에 할당했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹은 관련 클라이언트에서 추가 기능을 볼 수 있습니다.  <br/> |
|**해제됨**  <br/> |관리자가 추가 기능을 해제했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.  <br/> 추가 기능 상태가 활성으로 변경되면 사용자 및 그룹이 추가 기능에 다시 액세스할 수 있습니다.  <br/> |
|**삭제됨**  <br/> |관리자가 추가 기능을 삭제했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.  <br/> |
   
더 이상 추가 기능을 사용하는 사용자가 없는 경우 추가 기능을 삭제하는 것이 있습니다. 예를 들어 추가 기능을 해제하면 특정 연도의 특정 시간 동안에만 추가 기능을 사용하는 것이 나을 수 있습니다.

## <a name="delete-an-add-in"></a>추가 기능 삭제

배포된 추가 기능을 삭제할 수도 있습니다.

1. 관리 센터에서 설정 서비스 및 &  >  **페이지로 이동합니다.**

     > [!NOTE]
    > 관리 센터가 통합 앱으로 배포 환경으로 업데이트되고 있습니다. 위의 단계가 없는 경우 설정 통합 앱으로 이동하여 중앙 집중식 배포  >  **섹션으로 이동합니다.** On the top of the **Integrated apps** page, choose **Add-ins**.

2. 배포된 추가 기능을 선택합니다.

3. 추가 기능 **삭제 를 클릭합니다.** 오른쪽 아래 모서리에 있는 추가 기능 단추를 제거합니다.

4. 선택의 유효성을 검사하고 추가 기능 **제거 를 선택합니다.**

## <a name="edit-add-in-access"></a>추가 기능 액세스 편집

배포 후 관리자는 추가 기능의 사용자 액세스를 관리할 수도 있습니다.

1. 관리 센터에서 설정 서비스 및 &  >  **페이지로 이동합니다.**

     > [!NOTE]
    > 관리 센터가 통합 앱으로 배포 환경으로 업데이트되고 있습니다. 위의 단계가 없는 경우 설정 통합 앱으로 이동하여 중앙 집중식 배포  >  **섹션으로 이동합니다.** On the top of the **Integrated apps** page, choose **Add-ins**.

2. 배포된 추가 기능을 선택합니다.

3. 액세스 권한이 **있는** **사용자 아래에서 편집을 클릭합니다.**

4. 변경 내용을 저장합니다.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>모든 클라이언트에서 Office 스토어를 해제하여 추가 기능 다운로드 방지(Outlook 제외)

> [!NOTE]
> Outlook 추가 기능 설치는 다른 프로세스로 [관리됩니다.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)

조직에서는 Office 스토어에서 새 Office 추가 기능을 다운로드하지 못하게 할 수 있습니다. 중앙 집중식 배포와 함께 사용하면 조직에서 승인한 추가 기능만 조직 내의 사용자에게 배포할 수 있습니다.
  
**추가 기능 취득을 끄기 위해**
  
1. 관리 센터 미리 보기에서 **설정** \> [서비스 &amp; 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=2053743) 페이지로 이동합니다.

     > [!NOTE]
    > 관리 센터가 통합 앱으로 배포 환경으로 업데이트되고 있습니다. 위의 단계가 없는 경우 설정 통합 앱으로 이동하여 중앙 집중식 배포  >  **섹션으로 이동합니다.** On the top of the **Integrated apps** page, choose **Add-ins**.
    
3. 사용자 **소유 앱 및 서비스를 선택합니다.**
    
4. 사용자가 Office 스토어에 액세스할 수 있도록 하는 옵션을 선택 취소합니다.

이렇게 하면 모든 사용자가 스토어에서 다음 추가 기능을 다운로드할 수 없습니다.
  
- 다음의 Word, Excel 및 PowerPoint 2016용 추가 기능
    
  - Windows
    
  - Mac
    
  - 사무실
    
    
- **AppSource** 내에서 시작하여 취득
    
- Microsoft 365 내의 추가 기능
    
스토어에 액세스하는 사용자에게는 Office 스토어 추가 기능의 개별 취득을 방지하도록 **Microsoft 365가 구성됩니다.**
  
Office 스토어 끄기 지원은 다음 버전에서 사용할 수 있습니다.
  
- Windows: 16.0.9001 - 현재 사용할 수 있습니다.
    
- Mac: 16.10.18011401 - 현재 사용할 수 있습니다.
    
- iOS: 2.9.18010804 - 현재 사용할 수 있습니다.
    
- 웹 - 현재 사용할 수 있습니다.
    
이렇게 해서 관리자가 중앙 집중식 배포를 사용하여 Office 스토어에서 추가 기능을 할당할 수 있는 것은 아닙니다.
  
사용자가 Microsoft 계정으로 로그인하지 못하도록 조직 계정만 사용하도록 로그온을 제한할 수 있습니다. 자세한 내용은 [Office 2016의 ID, 인증](/DeployOffice/security/identity-authentication-and-authorization-in-office)및 권한 부여를 참조하세요.  

> [!NOTE]
> 사용자가 Office 스토어에 액세스하지 못하게 하면 테스트용 Office 추가 기능을 [테스트용으로 로드할 수 없습니다.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>추가 기능을 사용할 수 있는 최종 사용자 경험에 대한 자세한 내용은

추가 기능을 배포한 후 최종 사용자는 Office 응용 프로그램에서 추가 기능을 사용할 수 있습니다(Office 추가 기능 사용 시작 [참조).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 추가 기능은 추가 기능에서 지원하는 모든 플랫폼에 나타납니다.
  
추가 기능이 추가 기능 명령을 지원하는 경우 명령은 Office 리본에 나타납니다. 다음 예에서는 **인용 검색** 명령이 **인용** 추가 기능에 나타납니다. 

![검색 인설이 있는 Office 리본 메뉴](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
배포된 추가 기능에서 추가 기능 명령을 지원하지 않는 경우 또는 배포된 모든 추가 기능을 보거나 내 추가 기능을 통해 볼 **수 있습니다.** 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016, Excel 2016 또는 PowerPoint 2016의 경우

1. 내 **추가 \> 기능 삽입을 선택합니다.** 
    
2. Office 추가 기능 창에서 **관리자가 관리함** 탭을 선택합니다. 
    
3. 이전에 배포한 추가 기능을 두 번 클릭합니다(이 예에서는 **인용** ). <br/>![Office 추가 기능 페이지의 관리 탭](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook의 경우

1. 홈 **리본에서** 추가 기능 **사용 을 선택합니다.**<br/>![Outlook의 스토어 단추](../../media/getaddinsicon.png)
  
2. 왼쪽 **내비게이트에서** 관리자 관리 를 선택합니다. 

## <a name="learn-more"></a>자세히 알아보기

[관리 센터에서 추가 기능 배포](./manage-deployment-of-add-ins.md)

[Office 추가 기능](/office/dev/add-ins/overview/office-add-ins)을 만들고 빌드하는 방법에 대해 자세히 알아보세요.
  
[중앙 집중식 배포 PowerShell cmdlet을](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)사용하여 추가 기능을 관리합니다.
  
[문제 해결: 사용자가 추가 기능을 볼 수 없습니다.](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Microsoft Store에서 미성년자 및 추가 기능 다운로드](./minors-and-acquiring-addins-from-the-store.md)