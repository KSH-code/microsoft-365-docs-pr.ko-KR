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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 중앙 집중식 추가 기능을 사용하여 조직의 사용자 및 그룹에 추가 기능을 배포하는 방법을 학습합니다.
ms.openlocfilehash: 4dd2cbc842d10770b544df014685173a8888df67
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184499"
---
# <a name="manage-add-ins-in-the-admin-center"></a>관리 센터에서 추가 기능 관리

Office 추가 기능을 사용하면 문서를 개인 설정하고 웹의 정보에 액세스하는 방법을 간소화할 수 [있습니다(추가](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)기능 사용 시작 Office 참조). 

관리자가 조직의 사용자에 대해 추가 기능을 배포한 후 추가 기능을 해제하거나 설정하고, 추가 기능 액세스 권한을 편집, 삭제 및 관리할 수 있습니다.

관리 센터에서 추가 기능을 설치하는 데 대한 자세한 내용은 관리 센터에서 추가 기능 [배포를 참조하세요.](./manage-deployment-of-add-ins.md)
  
## <a name="add-in-states"></a>추가 기능 상태

추가 기능의 상태는 **On** 또는 **Off 상태일 수** 있습니다.
  
| 시/도 | 상태가 적용되는 경우 | 영향 |
|:-----|:-----|:-----|
|**활성**  <br/> |관리자가 추가 기능을 업로드하고 사용자 또는 그룹에 할당했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹은 관련 클라이언트에서 추가 기능을 볼 수 있습니다.  <br/> |
|**해제됨**  <br/> |관리자가 추가 기능을 해제했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.  <br/> 추가 기능 상태가 활성으로 변경되면 사용자 및 그룹이 추가 기능에 다시 액세스할 수 있습니다.  <br/> |
|**삭제됨**  <br/> |관리자가 추가 기능을 삭제했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.  <br/> |
   
더 이상 추가 기능을 사용하는 사용자가 없는 경우 추가 기능을 삭제하는 것이 있습니다. 예를 들어 추가 기능을 해제하면 특정 연도의 특정 시간 동안에만 추가 기능을 사용하는 것이 나을 수 있습니다.

## <a name="delete-an-add-in"></a>추가 기능 삭제

배포된 추가 기능을 삭제할 수도 있습니다.

1. 관리 센터에서 설정 서비스 &  >  **페이지로 이동합니다.**

    > [!NOTE]
    > 통합 앱을 통해 관리 센터에서 추가 기능을 [배포할 수도 있습니다.](test-and-deploy-microsoft-365-apps.md) 통합 앱은 전역 관리자 및 관리자에게 Exchange 표시됩니다. 위의 단계가 없는 경우 통합 앱으로 이동하여 중앙 **집중식 배포 섹션으로 설정**  >  **합니다.** On the top of the **Integrated apps** page, choose **Add-ins**.

2. 배포된 추가 기능을 선택합니다.

3. 추가 기능 **삭제 를 클릭합니다.** 오른쪽 아래 모서리에서 추가 기능 단추를 제거합니다.

4. 선택한 항목을 확인하고 **추가 기능 제거** 를 선택합니다.

## <a name="edit-add-in-access"></a>추가 기능 액세스 편집

배포 후 관리자는 추가 기능의 사용자 액세스를 관리할 수도 있습니다.

1. 관리 센터에서 설정 서비스 &  >  **페이지로 이동합니다.**

    > [!NOTE]
    > 통합 앱을 통해 관리 센터에서 추가 기능을 [배포할 수도 있습니다.](test-and-deploy-microsoft-365-apps.md) 통합 앱은 전역 관리자 및 관리자에게 Exchange 표시됩니다. 위의 단계가 없는 경우 통합 앱으로 이동하여 중앙 **집중식 배포 섹션으로 설정**  >  **합니다.** On the top of the **Integrated apps** page, choose **Add-ins**.


2. 배포된 추가 기능을 선택합니다.

3. Access가  있는 Who **편집을 클릭합니다.**

4. 변경 내용을 저장합니다.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>모든 클라이언트에서 Office Store를 해제하여 추가 기능 다운로드 방지(Outlook)

> [!NOTE]
> Outlook 추가 기능 설치는 다른 프로세스로 [관리됩니다.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)

조직에서는 Office 스토어에서 새 추가 기능을 다운로드하지 Office 있습니다. 중앙 집중식 배포와 함께 사용하면 조직에서 승인한 추가 기능만 조직 내의 사용자에게 배포할 수 있습니다.
  
**추가 기능 취득을 끄기 위해**
  
1. 관리 센터 미리 보기에서 **설정** \> [서비스 &amp; 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=2053743) 페이지로 이동합니다.

    > [!NOTE]
    > 통합 앱을 통해 관리 센터에서 추가 기능을 [배포할 수도 있습니다.](test-and-deploy-microsoft-365-apps.md) 통합 앱은 전역 관리자 및 관리자에게 Exchange 표시됩니다. 위의 단계가 없는 경우 통합 앱으로 이동하여 중앙 **집중식 배포 섹션으로 설정**  >  **합니다.** On the top of the **Integrated apps** page, choose **Add-ins**.

    
3. **사용자 소유 애플리케이션 및 서비스** 를 선택하세요.
    
4. 사용자가 Office Store에 액세스할 수 있도록 하려면 이 옵션을 선택 취소합니다.

    이렇게 하면 모든 사용자가 스토어에서 다음 추가 기능을 다운로드할 수 없습니다.
      
    - Word, Excel 및 PowerPoint 2016 추가 기능:
        
      - Windows
      - Mac
      - 사무실
        
        
    - **AppSource** 내에서 시작하여 취득
        
    - Microsoft 365
        
    스토어에 액세스하는 사용자에게는 "죄송합니다Microsoft 365 스토어 추가 기능을 개별적으로 Office 수 **없습니다.**
  
다음 버전에서는 Office 스토어를 끄는 기능을 사용할 수 있습니다.
  
- Windows: 16.0.9001 - 현재 사용 가능.
    
- Mac: 16.10.18011401 - 현재 사용할 수 있습니다.
    
- iOS: 2.9.18010804 - 현재 사용할 수 있습니다.
    
- 웹 - 현재 사용할 수 있습니다.
    
이렇게 해서 관리자가 중앙 집중식 배포를 사용하여 중앙 저장소에서 추가 기능을 할당하는 Office 않습니다.

> [!NOTE] 
> Visio 데이터 시각화 도우미, Bing 지도, 사용자 Graph 등의 추가 기능도 관리자가 스토어를 사용하지 않도록 설정한 경우에도 리본 메뉴에 계속 표시됩니다. 이러한 링크를 제거하려면 관리자가 GPO(그룹 정책 개체)를 통해 스토어를 사용하지 않도록 설정해야 합니다.
  
사용자가 Microsoft 계정으로 로그인하지 못하도록 조직 계정만 사용하도록 로그온을 제한할 수 있습니다. 자세한 내용은 [2016 에서 ID, 인증 및 권한 부여를 Office 참조하세요.](/DeployOffice/security/identity-authentication-and-authorization-in-office)  

> [!NOTE] 
> 사용자가 사무실 저장소에 액세스하지 못하게 하면 네트워크 공유에서 테스트를 위해 추가 Office 테스트용 [테스트용 로드를 방지할 수 있습니다.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>추가 기능의 최종 사용자 경험에 대한 자세한 내용은

추가 기능을 배포한 후 최종 사용자는 자신의 Office 응용 프로그램에서 사용할 수 있습니다(추가 기능 사용 시작 Office [참조).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 추가 기능은 추가 기능에서 지원하는 모든 플랫폼에 나타납니다.
  
추가 기능이 추가 기능 명령을 지원하는 경우 명령은 Office 리본에 나타납니다. 다음 예에서는 **인용 검색** 명령이 **인용** 추가 기능에 나타납니다. 

![Office 인용이 있는 리본 메뉴를 탐색합니다.](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
배포된 추가 기능에서 추가 기능 명령을 지원하지 않는 경우 또는 배포된 모든 추가 기능을 보거나 내 추가 기능을 통해 볼 **수 있습니다.** 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016, Excel 2016 또는 PowerPoint 2016의 경우

1. 내 **추가 \> 기능 삽입을 선택합니다.** 
    
2. Office 추가 기능 창에서 **관리자가 관리함** 탭을 선택합니다. 
    
3. 앞에서 배포한 추가 기능(이 예에서는 **인용)을** 두 번 클릭합니다.

    ![추가 기능 페이지의 관리 Office 탭입니다.](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook의 경우

1. 홈 **리본에서** 추가 기능 **사용 을 선택합니다.**

    ![저장소 단추를 Outlook.](../../media/getaddinsicon.png)
  
2. 왼쪽 탐색기에서 **관리되는 관리자** 를 선택합니다. 

## <a name="related-content"></a>관련 콘텐츠

[관리 센터에서](./manage-deployment-of-add-ins.md) 추가 기능 배포(문서)\
추가 기능 만들기 및 구축에 대해 자세히 Office 추가 [기능](/office/dev/add-ins/overview/office-add-ins) 만들기(문서)\
[중앙 집중식 배포 PowerShell cmdlet을](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) 사용하여 추가 기능 관리(문서)\
[문제 해결: 추가](/office365/troubleshoot/access-management/user-not-seeing-add-ins) 기능을 볼 수 없는 사용자(문서)\
[미성년자](./minors-and-acquiring-addins-from-the-store.md) 및 사용자로부터 추가 Microsoft Store(문서)
