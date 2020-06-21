---
title: 관리 센터의 추가 기능 배포 관리
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
ms.openlocfilehash: 25a4cd4147f6388cdbd8982eb10624e7b7e8f6cb
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780124"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 추가 기능 배포 관리

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

Office 추가 기능을 사용하면 문서를 개인 설정하고 웹에서 정보에 액세스하는 방법을 간소화할 수 있습니다([Office 추가 기능 사용 시작](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 참조). 관리자는 조직의 사용자를 위한 Office 추가 기능을 배포할 수 있습니다. Microsoft 365 관리 센터의 중앙 집중식 배포 기능을 사용 하 여이 작업을 수행할 수 있습니다.
  
중앙 집중식 배포는 대부분의 관리자가 조직 내에서 사용자 및 그룹에 추가 기능을 배포 하는 데 권장 되 고 기능이 풍부한 방법입니다. 조직에서 중앙 집중식 배포를 지원할 수 있는지를 확인 하는 방법에 대 한 자세한 내용은 [추가 기능의 중앙 집중식 배포가 조직에 작동 하는지 확인](centralized-deployment-of-add-ins.md)을 참조 하십시오.
  
중앙 집중식 배포는 다음과 같은 이점을 제공합니다.
  
- 전역 관리자는 추가 기능을 사용자에 게 직접 할당 하거나, 그룹을 통해 여러 사용자에 게 또는 테 넌 트의 모든 사람에 게 할당할 수 있습니다.
    
- When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.
    
- 관리자가 추가 기능을 해제 하거나 삭제 하거나, 사용자가 Azure Active Directory 또는 추가 기능이 할당 된 그룹에서 제거 된 경우에는 사용자에 게 더 이상 추가 기능이 나타나지 않습니다.
    
> [!NOTE]
>  Word에서 Excel 및 PowerPoint는 [Sharepoint 앱 카탈로그](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 를 사용 하 여 온-프레미스 환경의 사용자에 게 추가 기능을 배포 하 고, Microsoft 365 및/또는 sharepoint 추가 기능에 대 한 지원에는 연결 하지 않습니다. Outlook의 > Exchange 제어판을 사용 하 여 Microsoft 365에 연결 하지 않고 온-프레미스 환경에 배포 합니다. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Office 추가 기능 배포에 권장되는 방법

Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:
  
1. Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.
    
2. Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.
    
3. 사용자 대상 그룹에 전체 배포합니다.
    
대상 그룹의 크기에 따라 배포 단계를 추가하거나 제거할 수 있습니다.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>관리 센터를 사용 하 여 Office 추가 기능 배포

시작 하기 전에 [추가 기능의 중앙 집중식 배포가 조직에 작동 하는지 확인](centralized-deployment-of-add-ins.md)을 참조 하세요.

  
1. 관리 센터에서 **설정** \> **추가 기능** 페이지로 이동 합니다.
    
2. 페이지 맨 위에 있는 **추가 기능 배포** 를 선택 합니다. 개요 페이지에서 **다음**을 선택 합니다.
    
3. 옵션을 선택 하 고 지침을 따릅니다.
  
4. Office 스토어에서 추가 기능을 추가 하는 옵션을 선택한 경우 이제 추가 기능을 선택할 수 있습니다. **추천 항목**, **평가** 또는 **이름** 범주를 통해 사용 가능한 추가 기능을 볼 수 있습니다. Office 스토어에서는 무료 추가 기능만 추가할 수 있습니다. 유료 추가 기능은 현재 지원되지 않습니다. 추가 기능을 선택한 후에는 몇 가지 추가 약관에 동의 하 여 진행 해야 합니다. <br/><br/> 참고: Office 스토어 옵션을 사용 하면 사용자가 작업을 수행 하지 않고도 추가 기능에 대 한 업데이트 및 향상 기능을 자동으로 사용할 수 있습니다.

5. 다음 페이지에서 **모든 사용자**, **특정 사용자/그룹** 또는 **자신만** 을 선택 하 여 추가 기능을 배포할 사용자를 지정 합니다. 추가 기능을 배포할 사용자 또는 그룹을 찾으려면 검색 상자를 사용합니다. <br/>참고: 추가 기능에 적용 되는 다른 상태에 대해 알아봅니다. 이 항목의 뒷부분에 나오는 [추가 기능 상태](#add-in-states)를 참조하세요.
  
6. **배포**를 선택 합니다.
  
7. 추가 기능이 배포 되 면 녹색 눈금이 표시 됩니다. 페이지에 설명 된 지침에 따라 추가 기능이 성공적으로 배포 되었는지 테스트할 수 있습니다.

> [!NOTE]
> 앱의 리본 메뉴에 추가 기능 아이콘이 표시 되도록 하려면 Office를 다시 열어야 할 수도 있습니다. Outlook 추가 기능은 사용자의 리본에 표시 되는 데 최대 24 시간이 걸릴 수 있습니다.
    
8. 완료 되 면 **다음**을 선택 합니다. 자신에 게 배포한 경우 **추가 기능에 액세스할** 수 있는 사용자를 선택 하 여 다른 사용자에 게 배포 합니다.



사용자가 아닌 다른 조직의 구성원에 게 추가 기능을 배포한 경우 추가 기능의 배포를 효과적으로 알리기 위해 표시 된 지침을 따르세요. <br/>이제 Microsoft 365에서 추가 기능이 다른 앱과 함께 표시 됩니다.
  
추가 기능을 배포한 사용자 및 그룹에 이제 추가 기능을 사용할 수 있다는 사실을 알려 주는 것이 좋습니다. 추가 기능을 사용하는 경우 및 방법을 설명하고 추가 기능이 업무 수행에 어떻게 도움이 될 수 있는지를 설명하는 전자 메일을 해당 사용자 및 그룹에 보내는 것을 고려하세요. 사용자에 게 추가 기능에 문제가 있는 경우 도움이 될 수 있는 관련 도움말 콘텐츠 또는 Faq를 포함 하거나 연결 합니다.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>사용자 및 그룹에 추가 기능을 할당할 때 고려 사항

Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:
  
- **Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization. 
    
- **Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users. 
    
- **Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin. 

- **자신만: 추가**기능을 자신만에 게 할당 하면 사용자의 계정에만 추가 기능이 할당 됩니다. 이 방법은 먼저 추가 기능을 테스트 하려는 경우에 유용 합니다.
    
조직에 적합 한 옵션은 구성에 따라 달라 집니다. 그러나 그룹을 통해 할당하는 것이 좋습니다. 관리자의 입장에서는 할당된 사용자를 매번 변경하는 것보다 그룹을 사용하여 관리하고 해당 그룹의 구성원 자격을 관리하는 편이 더 쉽습니다. 반면 액세스 권한을 극소수의 사용자만으로 제한하고, 따라서 특정 사용자에 대한 할당을 수행하려고 하는 경우가 있습니다. 이러한 경우에는 할당된 사용자를 수동으로 관리해야 합니다.
  
### <a name="add-in-states"></a>추가 기능 상태

추가 기능이 **설정** 또는 **해제** 상태일 수 있습니다.
  
|**상태**|**상태가 적용되는 경우**|**영향**|
|:-----|:-----|:-----|
|**활성**  <br/> |관리자가 추가 기능을 업로드 하 고 사용자 또는 그룹에 할당 했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹은 관련 클라이언트에서 추가 기능을 볼 수 있습니다.  <br/> |
|**해제됨**  <br/> |관리자가 추가 기능을 해제했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.  <br/> 추가 기능 상태가 활성으로 변경되면 사용자 및 그룹이 추가 기능에 다시 액세스할 수 있습니다.  <br/> |
|**삭제됨**  <br/> |관리자가 추가 기능을 삭제했습니다.  <br/> |추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.  <br/> |
   
추가 기능 중 아무도 사용 하지 않는 경우에는 삭제 하는 것이 좋습니다. 추가 기능 해제는 1년 중 특정 시간에만 추가 기능이 사용되는 경우에 적합할 수 있습니다.
  
### <a name="security-of-office-add-ins"></a>Office 추가 기능의 보안

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- 데이터를 표시합니다.
    
- 사용자 문서를 읽어 상황에 맞는 서비스를 제공합니다.
    
- 사용자 문서에서 데이터를 읽고 기록하여 해당 사용자에게 값을 제공합니다.
    
Office 추가 기능의 유형 및 기능에 대한 자세한 내용은 [Office 추가 기능 플랫폼 개요](https://go.microsoft.com/fwlink/p/?linkid=846362)에서, 특히 "Office 추가 기능 분석" 섹션을 참조하세요.
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
추가 기능에 대한 업데이트는 다음과 같이 발생합니다.
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > 관리자는 업데이트를 수행 하는 데 필요한 LOB 추가 기능을 제거할 필요가 없습니다.   추가 기능 섹션에서 관리자는 LOB 추가 기능을 클릭 하 고 오른쪽 아래 모서리에 있는 **업데이트 단추** 를 선택 하면 됩니다. 새 추가 기능의 버전이 기존 추가 기능의 버전과 동일 하지 않은 경우에만 업데이트를 사용할 수 있습니다.   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

### <a name="edit-add-in-access"></a>추가 기능 액세스 편집

배포 후 관리자는 추가 기능에 대 한 사용자 액세스를 수정할 수도 있습니다.

1. 관리 센터에서 **설정**  >  **서비스 & 추가** 기능 페이지로 이동 합니다.

2. 배포 된 추가 기능을 선택 합니다.

3. **액세스 권한이 있는 사용자**아래에서 **편집** 을 클릭 합니다.
4. 변경 내용을 저장 합니다.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>모든 클라이언트로부터 Office 스토어를 꺼서 추가 기능 다운로드 방지 (Outlook 제외)

> [!NOTE]
> Outlook 추가 기능 설치는 [다른 프로세스](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)를 통해 관리 됩니다.

조직에서는 Office 스토어에서 새 Office 추가 기능을 다운로드 하지 못하도록 할 수 있습니다. 이를 중앙 집중식 배포와 함께 사용 하 여 조직 내에서 사용자에 게 승인 된 추가 기능만 배포 되도록 할 수 있습니다.
  
추가 기능 취득 기능을 해제 하려면
  
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
  
사용자가 Microsoft 계정으로 로그인 하지 못하게 하기 위해 조직 계정만 사용 하도록 로그온을 제한할 수 있습니다. 자세한 내용은 [여기](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)를 확인 하세요.
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>미성년자가을 사용 하 여 스토어에서 추가 기능 가져오기

GDPR (일반 데이터 보호 규정)은 실제 5 월 25 일 2018이 되는 유럽 연합 규정입니다. 사용자에 게 해당 데이터에 대 한 권한을 부여 하 고 보호 합니다. GDPR의 특징 중 하나는 미성년자가가 자신의 부모 또는 보호를 승인 하지 않은 파티에 개인 데이터를 보낼 수 없다는 것입니다. 약간만 정의 되는 특정 기간은 개인이 있는 지역에 따라 달라 집니다.
  
자녀 보호에 대 한 법적 규정이 있는 지역에는 미국, 대한민국, 영국 및 유럽 연합 등이 있습니다. 이러한 지역의 경우 저장소에서 새 Office 추가 기능을 가져오는 작업과 이전에 획득 한 추가 기능을 실행 하는 것을 Azure Active Directory를 통해 차단 합니다. 법적 규정이 없는 국가의 경우에는 다운로드 제한이 없습니다.
  
사용자는 Azure Active Directory에 지정 된 데이터를 기반으로 하는 부 버전으로 확인 됩니다. 테 넌 트 관리자는 해당 사용자의 법적 연령 그룹 및 자녀 보호를 선언 합니다.
  
특정 추가 기능을 사용 하 여 부모/보호자를 consents 하는 경우 테 넌 트 관리자는 중앙 집중식 배포를 사용 하 여 사용자가 동의 하는 모든 미성년자가에 해당 추가 기능을 배포할 수 있습니다.
  
미성년자가에 대 한 GDPR을 준수 하려면 학교/조직에 Office의 다음 빌드 중 하나가 배포 되었는지 확인 해야 합니다.
  
 **Word, Excel, PowerPoint 및 Project에 대해**다음을 수행 합니다. 
  
|||
|:-----|:-----|
|**플랫폼** <br/> |**빌드 번호** <br/> |
|Microsoft 365 Apps for enterprise (현재 채널)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (반기 엔터프라이즈 채널)  <br/> |8431.2159  <br/> |
|Windows 용 Office 2016  <br/> |16.0.4672.1000  <br/> |
|Windows 용 Office 2013  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|웹에 대 한 Office  <br/> |해당 없음  <br/> |
   
 **Outlook의 경우**: 
  
|||
|:-----|:-----|
|**플랫폼** <br/> |**빌드 번호** <br/> |
|Windows 용 Outlook 2016 (MSI)  <br/> |TBD 만들기  <br/> |
|C2R (Windows 용 Outlook 2016)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|IOS 용 Outlook 모바일  <br/> |2.75.0  <br/> |
|Android 용 Outlook 모바일  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |해당 없음  <br/> |
   
 **Office 2013 요구 사항**
  
Windows 용 Word, Excel 및 PowerPoint 2013은 ADAL (Active Directory 인증 라이브러리)을 사용 하는 경우 동일한 사소한 검사를 지원 합니다. 다음에 설명 된 대로 준수에 대 한 두 가지 옵션이 있습니다.
  
- **ADAL을 사용 하도록 설정**합니다. 이 문서에서는 Office [365](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)2013에 대해 ADAL을 사용 하도록 설정 하는 방법에 대해 설명 합니다.<br/>또한 [Windows 장치에서 Office 2013에 대 한 최신 인증 사용](../security-and-compliance/enable-modern-authentication.md)에 설명 된 대로 ADAL을 사용 하도록 레지스트리 키를 설정 해야 합니다.<br/>또한 Office 2013에 대 한 다음 4 월 업데이트를 설치 해야 합니다.
    
  - [Office 2013의 보안 업데이트에 대 한 설명: 2018 년 4 월 10 일](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [4 월 3 일, 2018, Office 2013 업데이트 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **ADAL을 사용 하지 않도록 설정**합니다. Office 2013에서 ADAL을 사용 하도록 설정할 수 없는 경우 그룹 정책을 사용 하 여 office 클라이언트에 대 한 저장소를 해제 하는 것이 좋습니다. Office 용 앱 설정을 해제 하는 방법에 대 한 정보는 [여기](https://technet.microsoft.com/library/cc178992.aspx)에 있습니다.
    
## <a name="end-user-experience-with-add-ins"></a>추가 기능에 대한 최종 사용자 환경

Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). The add-in will appear on all platforms that the add-in supports.
  
If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in. 

![검색 인용이 있는 Office 리본 메뉴](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
배포 된 추가 기능이 추가 기능 명령을 지원 하지 않거나 배포한 모든 추가 기능을 보려는 경우 **내 추가 기능**을 통해 볼 수 있습니다. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016, Excel 2016 또는 PowerPoint 2016의 경우

1. ** \> 내 추가 기능 삽입을**선택 합니다. 
    
2. Office 추가 기능 창에서 **관리자가 관리함** 탭을 선택합니다. 
    
3. 이전에 배포한 추가 기능을 두 번 클릭합니다(이 예에서는 **인용** ). <br/>![Office 추가 기능 페이지의 관리 관리 탭](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook의 경우

1. **홈** 리본에서 **추가 기능 가져오기를**선택 합니다.<br/>![Outlook의 스토어 단추](../../media/getaddinsicon.png)
  
2. 왼쪽 탐색 창에서 **관리-관리** 를 선택 합니다.

## <a name="delete-the-add-in"></a>추가 기능 삭제

배포 된 추가 기능을 삭제할 수도 있습니다.

1. 관리 센터에서 **설정**  >  **서비스 & 추가** 기능 페이지로 이동 합니다.

2. 배포 된 추가 기능을 선택 합니다.

3. **추가 기능 삭제**를 클릭 합니다. 오른쪽 아래 모서리에 있는 추가 기능 단추를 제거 합니다.
4. 선택한 항목의 유효성을 검사 하 고 **추가 기능 제거**를 선택 합니다.
  
## <a name="learn-more"></a>자세히 알아보기

[Office 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=846362)을 만들고 빌드하는 방법에 대해 자세히 알아보세요.
  
[중앙 집중식 배포 PowerShell cmdlet을 사용 하 여 추가 기능을 관리](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)합니다.
  
[문제 해결: 사용자가 추가 기능을 볼 수 없음](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
