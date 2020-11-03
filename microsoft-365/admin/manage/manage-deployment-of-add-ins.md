---
title: 관리 센터에서 추가 기능 배포
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
ms.openlocfilehash: 9708ec9877c4d07b0cf93ea9d6815303236eff4b
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830640"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>관리 센터에서 추가 기능 배포

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

Office 추가 기능을 사용하면 문서를 개인 설정하고 웹에서 정보에 액세스하는 방법을 간소화할 수 있습니다([Office 추가 기능 사용 시작](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 참조). 관리자는 Microsoft 365 관리 센터의 중앙 집중식 배포 기능을 사용 하 여 조직의 사용자를 위한 Office 추가 기능을 배포할 수 있습니다. 중앙 집중식 배포는 대부분의 관리자가 조직 내에서 사용자 및 그룹에 추가 기능을 배포 하는 데 권장 되 고 기능이 풍부한 방법입니다. 

조직에서 중앙 집중식 배포를 지원할 수 있는지를 확인 하는 방법에 대 한 자세한 내용은 [추가 기능의 중앙 집중식 배포가 조직에 작동 하는지 확인](centralized-deployment-of-add-ins.md)을 참조 하십시오.

배포 후에 추가 기능을 관리 하는 방법에 대 한 자세한 내용은 [administration center에서 추가 기능 관리](manage-addins-in-the-admin-center.md) 를 참조 하세요.
  
> [!NOTE]
>  Word에서 Excel 및 PowerPoint는 [Sharepoint 앱 카탈로그](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 를 사용 하 여 온-프레미스 환경의 사용자에 게 추가 기능을 배포 하 고, Microsoft 365 및/또는 sharepoint 추가 기능에 대 한 지원에는 연결 하지 않습니다. Outlook의 경우 Exchange 제어판을 사용 하 여 Microsoft 365에 연결 하지 않고 온-프레미스 환경에 배포 합니다.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Office 추가 기능 배포에 권장되는 방법

단계별 방법을 사용 하 여 추가 기능을 롤아웃하기 위해 다음을 수행 하는 것이 좋습니다.
  
1. 소규모 비즈니스 관련자 및 IT 부서의 구성원에 게 추가 기능을 배포 합니다. 배포가 성공한 경우 2 단계로 이동 합니다.
    
2. 비즈니스 내의 더 많은 사용자에 게 추가 기능을 배포 합니다. 다시 결과를 평가 하 고 성공한 경우 전체 배포를 계속 진행 합니다.
    
3. 모든 사용자에 대해 전체 롤아웃을 수행 합니다.
    
대상 그룹의 크기에 따라 롤아웃 단계를 추가 하거나 제거할 수 있습니다.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>관리 센터를 사용 하 여 Office 추가 기능 배포

시작 하기 전에 [추가 기능의 중앙 집중식 배포가 조직에 작동 하는지 확인](centralized-deployment-of-add-ins.md)을 참조 하세요.
  
1. 관리 센터에서 **설정** \> **추가 기능** 페이지로 이동 합니다. **추가 기능** 페이지가 표시 되지 않으면 **Settings** \> **통합 앱** \> **추가 기능** 설정 페이지로 이동 합니다.
    
2. 페이지 맨 위에 있는 **추가 기능 배포** 를 선택 하 고 **다음** 을 선택 합니다.
 
    > [!NOTE]
    > 관리 센터는 통합 앱을 사용 하 여 배포 환경으로 업데이트 됩니다. 위의 단계를 볼 수 없는 경우 **설정**  >  **통합 앱** 으로 이동 하 여 중앙 집중식 배포 섹션으로 이동 합니다. **통합 앱** 페이지 위쪽에서 **추가 기능** 을 선택 합니다.
    
3. 옵션을 선택 하 고 지침을 따릅니다.
  
4. Office 스토어에서 추가 기능을 추가 하는 옵션을 선택한 경우 추가 기능을 선택 합니다. </br>

    사용 가능한 추가 기능은 범주별로 볼 수 있습니다 (예: **추천 단어** , **평점** 또는 **이름** ). Office 스토어에서는 무료 추가 기능만 사용할 수 있습니다. 유료 추가 기능은 현재 지원되지 않습니다. 추가 기능을 선택한 후에는 계속 진행할 사용권 조항에 동의 합니다. <br/> 

    > [!NOTE] 
    > Office 스토어 옵션을 사용 하면 업데이트 및 향상 된 기능이 사용자에 게 자동으로 배포 됩니다.

5. 다음 페이지에서 **모든 사용자** , **특정 사용자/그룹** 또는 자신만을 선택 하 여 추가 기능을 배포할 **사용자를 지정** 합니다. 검색 상자를 사용 하 여 특정 사용자 또는 그룹을 찾습니다. <br/>

    > [!NOTE] 
    > 추가 기능에 적용 되는 다른 상태에 대 한 자세한 내용은 [추가 기능 상태](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)를 참조 하세요.
  
6. **배포** 를 선택 합니다.
  
7. 추가 기능이 배포 되 면 녹색 눈금이 나타납니다. 페이지 지시에 따라 추가 기능을 테스트 합니다.

    > [!NOTE]
    > 사용자가 앱 리본 메뉴에서 추가 기능 아이콘을 보려면 Office를 다시 열어야 할 수도 있습니다. Outlook 추가 기능은 앱 리본에 표시 되는 데 최대 24 시간이 걸릴 수 있습니다.
    
8. 완료 되 면 **다음** 을 선택 합니다. 자신에 게 배포한 경우 **추가 기능에 액세스할** 수 있는 사용자를 선택 하 여 더 많은 사용자에 게 배포할 수도 있습니다.

    조직의 다른 구성원에 게 추가 기능을 배포한 경우 지침에 따라 추가 기능의 배포를 공지 합니다. <br/>
  
    배포 된 추가 기능을 사용할 수 있음을 사용자와 그룹에 게 알리는 것이 좋습니다. 추가 기능을 사용 하는 시기와 방법을 설명 하는 전자 메일을 보내는 것이 좋습니다. 추가 기능에 문제가 있는 경우 사용자에 게 도움이 될 수 있는 도움말 콘텐츠 또는 Faq를 포함 하거나 연결 합니다.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>사용자 및 그룹에 추가 기능을 할당할 때 고려 사항

관리자는 모든 사용자 또는 특정 사용자 및 그룹에 추가 기능을 할당할 수 있습니다. 각 옵션은 다음과 같은 영향을 줍니다.
  
- **모든 사용자** 이 옵션은 조직의 모든 사용자에 게 추가 기능을 할당 합니다. 이 옵션은 조직에 진정으로 범용인 추가 기능에 대해서만 사용합니다. 
    
- **사용자** 개별 사용자에 게 추가 기능을 할당 한 다음 새 사용자에 게 추가 기능을 배포 하는 경우 먼저 새 사용자를 추가 해야 합니다.
    
- **그룹** 그룹에 추가 기능을 할당 하면 해당 그룹에 추가 된 사용자에 게 자동으로 추가 기능이 할당 됩니다. 사용자가 그룹에서 제거 되 면 해당 사용자는 추가 기능에 대 한 액세스를 잃게 됩니다. 두 경우 모두 관리자가 추가 작업을 수행 하지 않아도 됩니다. 

- **자신만** 추가 기능을 자신만에 게 할당 하는 경우 추가 기능은 사용자의 계정에만 할당 되며,이는 추가 기능을 테스트 하는 데 가장 적합 합니다.
    
조직에 적합 한 옵션은 구성에 따라 다릅니다. 그러나 그룹을 사용 하 여 할당을 수행 하는 것이 좋습니다. 관리자는 그룹을 사용 하 고 매번 개별 사용자를 할당 하는 대신 해당 그룹의 구성원을 제어 하 여 추가 기능을 보다 쉽게 관리할 수 있습니다. 경우에 따라 사용자를 수동으로 할당 하 여 특정 사용자에 게 할당 하는 방법으로 소수의 사용자 에게만 액세스를 제한할 수 있습니다.
  
## <a name="more-about-office-add-ins-security"></a>Office 추가 기능 보안에 대 한 자세한 정보

Office 추가 기능은 추가 기능에 대한 일부 메타데이터를 포함하지만 무엇보다도 모든 코드와 논리가 포함된 웹 응용 프로그램을 가리키는 XML 매니페스트 파일을 결합합니다. 추가 기능의 기능은 다양할 수 있습니다. 예를 들어 추가 기능은 다음과 같은 작업을 수행할 수 있습니다.
  
- 데이터를 표시합니다.
    
- 사용자 문서를 읽어 상황에 맞는 서비스를 제공합니다.
    
- 사용자 문서에서 데이터를 읽고 기록하여 해당 사용자에게 값을 제공합니다.
    
Office 추가 기능의 유형 및 기능에 대한 자세한 내용은 [Office 추가 기능 플랫폼 개요](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)에서, 특히 "Office 추가 기능 분석" 섹션을 참조하세요.
  
사용자 문서를 조작하려면 추가 기능이 필요한 사용 권한을 매니페스트에서 선언해야 합니다. 5개 수준으로 이루어진 JavaScript API 액세스 권한 모델은 작업창 추가 기능의 사용자에게 개인 정보 및 보안의 토대를 제공합니다. Office 스토어에 있는 대부분의 추가 기능은 ReadWriteDocument 수준이며, 거의 모든 추가 기능이 최소한 ReadDocument 수준을 지원합니다. 사용 권한 수준에 대한 자세한 내용은 [콘텐츠 및 작업창 추가 기능에서 사용되는 API에 대한 사용 권한 요청](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)을 참조하세요.
  
매니페스트를 업데이트하는 경우 일반적으로 추가 기능의 아이콘과 텍스트가 변경됩니다. 추가 기능 명령이 변경될 때도 있습니다. 그러나 추가 기능에 대한 사용 권한은 변경되지 않습니다. 추가 기능에 대한 모든 코드와 논리가 실행되는 웹 응용 프로그램은 언제든지 변경될 수 있으며, 이것이 웹 응용 프로그램의 특성입니다.
  
추가 기능에 대한 업데이트는 다음과 같이 발생합니다.
  
- **LOB(기간 업무) 추가 기능:** 관리자가 명시적으로 매니페스트를 업로드한 이러한 경우에는 추가 기능을 위해 관리자가 새 매니페스트 파일을 업로드하여 메타데이터 변경 내용을 지원해야 합니다. 다음에 관련 Office 응용 프로그램을 시작하면 추가 기능이 업데이트됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다. 

    > [!NOTE]
    > 관리자는 업데이트를 수행 하는 데 필요한 LOB 추가 기능을 제거할 필요가 없습니다.   추가 기능 섹션에서 관리자는 LOB 추가 기능을 클릭 하 고 오른쪽 아래 모서리에 있는 **업데이트 단추** 를 선택 하면 됩니다. 새 추가 기능의 버전이 기존 추가 기능의 버전과 동일 하지 않은 경우에만 업데이트를 사용할 수 있습니다.   
    
- **Office 스토어 추가 기능:** 관리자가 Office 스토어에서 추가 기능을 선택한 경우 Office 스토어에서 추가 기능이 업데이트되면 나중에 중앙 집중식 배포에서도 추가 기능이 업데이트됩니다. 다음에 관련 Office 응용 프로그램을 시작하면 추가 기능이 업데이트됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다. 
  
## <a name="learn-more"></a>자세히 알아보기

[관리 센터에서 추가 기능 관리](manage-addins-in-the-admin-center.md)

[Office 추가 기능 작성](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals)

[미성년자가을 사용 하 여 스토어에서 추가 기능 가져오기](minors-and-acquiring-addins-from-the-store.md)
  
[중앙 집중식 배포 PowerShell cmdlet을 사용 하 여 추가 기능 관리](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[문제 해결: 사용자가 추가 기능을 볼 수 없음](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
