---
title: 관리 센터에서 추가 기능 배포
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
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 관리 센터에서 중앙 집중식 배포를 사용하여 조직의 사용자 및 그룹에 추가 기능을 배포하는 방법을 설명합니다.
ms.openlocfilehash: 522a1884752e0ada6b43ba68a853cb117c8dfd75
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187195"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>관리 센터에서 추가 기능 배포

Office 추가 기능을 사용하면 문서를 개인 설정하고 웹에서 정보에 액세스하는 방법을 간소화할 수 있습니다([Office 추가 기능 사용 시작](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 참조). 관리자는 의 중앙 집중식 배포 기능을 사용하여 Office 사용자를 위한 추가 기능을 배포할 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터.</a> 중앙 집중식 배포는 대부분의 관리자가 조직 내의 사용자 및 그룹에 추가 기능을 배포하는 데 권장되는 가장 다양한 기능입니다.

조직에서 중앙 집중식 배포를 지원할 수 있는지 확인하는 방법에 대한 자세한 내용은 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조하세요.](centralized-deployment-of-add-ins.md)

배포 후 추가 기능 관리에 대한 자세한 내용은 관리 센터에서 추가 기능 [관리를 참조하세요.](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Word의 경우 Excel PowerPoint 및 SharePoint SharePoint [](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 카탈로그를 사용하여 Microsoft 365 및/또는 필요한 추가 기능을 지원하지 Microsoft 365 환경의 사용자에게 추가 기능을 배포합니다. 이 Outlook 제어판을 사용하여 Exchange 연결 없이 사내 환경에 배포할 Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Office 추가 기능 배포에 권장되는 방법

단계적 접근 방식을 사용하여 추가 기능을 롤아웃하기 위해 다음을 사용하는 것이 좋습니다.
  
1. 소수의 업무 관련자 및 IT 부서 구성원에게 추가 기능을 배포합니다. 배포에 성공하면 2단계로 이동하십시오.
    
2. 추가 기능을 비즈니스 내 더 많은 개인에게 롤아웃합니다. 다시 결과를 평가하고 성공하면 전체 배포를 계속합니다.
    
3. 모든 사용자에게 전체 롤아웃을 수행합니다.
    
대상 대상의 크기에 따라 롤아웃 단계를 추가하거나 제거할 수 있습니다.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>관리 센터를 사용하여 Office 추가 기능 배포

시작하기 전에 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조합니다.](centralized-deployment-of-add-ins.md)
  
1. 관리 센터에서 추가 기능 **설정** \> **이동합니다.** 추가 기능 페이지가  없는 경우 통합 앱 추가 **설정** \>  \> **페이지로 이동합니다.**

2. 페이지 **맨** 위에 있는 추가 기능 배포를 선택하고 다음 을 **선택합니다.**

    > [!NOTE]
    > 통합 앱을 통해 관리 센터에서 추가 기능을 [배포할 수도 있습니다.](test-and-deploy-microsoft-365-apps.md) 통합 앱은 전역 관리자 및 관리자에게 Exchange 표시됩니다. 위의 단계가 없는 경우 통합 앱으로 이동하여 중앙 **집중식 배포 섹션으로 설정**  >  **합니다.** On the top of the **Integrated apps** page, choose **Add-ins**.

3. 옵션을 선택하고 지침을 따릅니다.
  
4. 스토어에서 추가 기능을 추가하는 옵션을 선택한 Office 추가 기능을 선택합니다. </br>

    추천, 평점 또는 이름과 같은 범주별로 사용 가능한 추가 기능을 볼 수 **있습니다.** 무료 추가 기능만 스토어에서 Office 있습니다. 유료 추가 기능은 현재 지원되지 않습니다. 추가 기능을 선택한 후 계속할 사용 약관에 동의합니다. <br/> 

    > [!NOTE]
    > Office 스토어 옵션을 사용하면 업데이트 및 향상된 기능이 사용자에게 자동으로 배포됩니다.

5. 다음 페이지에서 **모든 사용자**, **특정 사용자/그룹** 또는 **해당 사용자만** 을 선택하여 추가 기능을 배포할 사용자를 지정하세요. 검색 상자를 사용하여 특정 사용자 또는 그룹을 찾을 수 있습니다. <br/>

    > [!NOTE]
    > 추가 기능에 적용되는 다른 상태는 추가 기능 상태 를 [참조합니다.](./manage-addins-in-the-admin-center.md)
  
6. **배포** 를 선택합니다.
  
7. 추가 기능을 배포하면 녹색 틱이 나타납니다. 페이지 지침에 따라 추가 기능을 테스트합니다.

    > [!NOTE]
    > 사용자는 앱 리본의 추가 Office 아이콘을 보기 위해 다시 실행해야 할 수 있습니다. Outlook 추가 기능을 앱 리본 메뉴에 표시하는 데 최대 24시간이 걸릴 수 있습니다.

8. 완료되면 다음 을 **선택합니다.** 자신만 배포한 경우 추가 기능 액세스  권한이 있는 사용자 변경을 선택하여 더 많은 사용자에게 배포할 수 있습니다.

    조직의 다른 구성원에게 추가 기능을 배포한 경우 지침에 따라 추가 기능 배포를 발표합니다. <br/>
  
    배포된 추가 기능을 사용할 수 있도록 사용자 및 그룹에 알리는 것이 좋습니다. 추가 기능을 사용하는 경우와 방법을 설명하는 전자 메일을 보낼 수 있습니다. 추가 기능 관련 문제가 있는 경우 사용자에게 도움이 될 수 있는 도움말 콘텐츠 또는 FAQ를 포함하거나 링크합니다.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>사용자 및 그룹에 추가 기능을 할당할 때 고려 사항

전역 관리자 및 Exchange 모든 사용자 또는 특정 사용자 및 그룹에 추가 기능을 할당할 수 있습니다. 각 옵션은 다음과 같은 영향을 줍니다.
  
- **모든 사람** 이 옵션은 조직의 모든 사용자에게 추가 기능을 할당합니다. 이 옵션은 조직에 진정으로 범용인 추가 기능에 대해서만 사용합니다.

- **사용자** 개별 사용자에게 추가 기능을 할당한 다음 새 사용자에게 추가 기능을 배포하는 경우 먼저 새 사용자를 추가해야 합니다.

- **그룹** 그룹에 추가 기능을 할당하면 그룹에 추가된 사용자에게 추가 기능의 할당이 자동으로 할당됩니다. 사용자가 그룹에서 제거되면 사용자는 추가 기능 액세스 권한을 잃게 됩니다. 두 경우 모두 관리자에게 추가 작업이 필요하지 않습니다.

- **나만** 추가 기능을 직접 할당하는 경우 추가 기능 테스트에 적합한 계정에만 추가 기능을 할당합니다.

조직에 적합한 옵션은 구성에 따라 다릅니다. 그러나 그룹을 사용하여 할당하는 것이 좋습니다. 관리자는 매월 개별 사용자를 할당하는 대신 그룹을 사용하고 해당 그룹의 구성원을 제어하여 추가 기능을 더 쉽게 관리할 수 있습니다. 경우에 따라 사용자를 수동으로 할당하여 특정 사용자에게 할당하여 소수의 사용자 집합에 대한 액세스를 제한할 수 있습니다.
  
## <a name="more-about-office-add-ins-security"></a>추가 Office 보안에 대한 자세한 정보

Office 추가 기능은 추가 기능에 대한 일부 메타데이터를 포함하지만 무엇보다도 모든 코드와 논리가 포함된 웹 응용 프로그램을 가리키는 XML 매니페스트 파일을 결합합니다. 추가 기능의 기능은 다양할 수 있습니다. 예를 들어 추가 기능은 다음과 같은 작업을 수행할 수 있습니다.
  
- 데이터를 표시합니다.

- 사용자 문서를 읽어 상황에 맞는 서비스를 제공합니다.

- 사용자 문서에서 데이터를 읽고 기록하여 해당 사용자에게 값을 제공합니다.

Office 추가 기능의 유형 및 기능에 대한 자세한 내용은 [Office 추가 기능 플랫폼 개요](/office/dev/add-ins/overview/office-add-ins)에서, 특히 "Office 추가 기능 분석" 섹션을 참조하세요.
  
사용자 문서를 조작하려면 추가 기능이 필요한 사용 권한을 매니페스트에서 선언해야 합니다. 5개 수준으로 이루어진 JavaScript API 액세스 권한 모델은 작업창 추가 기능의 사용자에게 개인 정보 및 보안의 토대를 제공합니다. Office 스토어에 있는 대부분의 추가 기능은 ReadWriteDocument 수준이며, 거의 모든 추가 기능이 최소한 ReadDocument 수준을 지원합니다. 사용 권한 수준에 대한 자세한 내용은 [콘텐츠 및 작업창 추가 기능에서 사용되는 API에 대한 사용 권한 요청](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)을 참조하세요.
  
매니페스트를 업데이트하는 경우 일반적으로 추가 기능의 아이콘과 텍스트가 변경됩니다. 추가 기능 명령이 변경될 때도 있습니다. 그러나 추가 기능에 대한 사용 권한은 변경되지 않습니다. 추가 기능에 대한 모든 코드와 논리가 실행되는 웹 응용 프로그램은 언제든지 변경될 수 있으며, 이것이 웹 응용 프로그램의 특성입니다.
  
추가 기능에 대한 업데이트는 다음과 같이 발생합니다.
  
- **LOB(기간 업무) 추가 기능:** 관리자가 명시적으로 매니페스트를 업로드한 이러한 경우에는 추가 기능을 위해 관리자가 새 매니페스트 파일을 업로드하여 메타데이터 변경 내용을 지원해야 합니다. 다음에 관련 Office 응용 프로그램을 시작하면 추가 기능이 업데이트됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다.

    > [!NOTE]
    > 관리자는 업데이트를 수행하기 위해 LOB 추가 기능을 제거할 필요가 없습니다.   추가 기능 섹션에서 관리자는 LOB 추가 기능을 클릭하고 오른쪽 아래  모서리에서 업데이트 단추를 선택할 수 있습니다. 업데이트는 새 추가 기능의 버전이 기존 추가 기능의 버전보다 큰 경우만 작동됩니다.

- **Office 스토어 추가 기능:** 관리자가 Office 스토어에서 추가 기능을 선택한 경우 Office 스토어에서 추가 기능이 업데이트되면 나중에 중앙 집중식 배포에서도 추가 기능이 업데이트됩니다. 다음에 관련 Office 응용 프로그램을 시작하면 추가 기능이 업데이트됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다.
  
## <a name="related-content"></a>관련 콘텐츠

[관리 센터에서](manage-addins-in-the-admin-center.md) 추가 기능 관리(문서)\
[첫 번째 Word 작업 창](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) 추가 기능 빌드(문서\
[스토어에서](minors-and-acquiring-addins-from-the-store.md) 미성년자 및 추가 기능 다운로드(문서)\
[중앙 집중식 배포 PowerShell cmdlet을](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) 사용하여 추가 기능 관리(문서)\
[문제 해결: 추가](/office365/troubleshoot/access-management/user-not-seeing-add-ins) 기능을 볼 수 없는 사용자(문서)
