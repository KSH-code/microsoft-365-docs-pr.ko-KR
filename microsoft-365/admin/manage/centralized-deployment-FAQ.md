---
title: 중앙 집중식 배포 FAQ
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
description: Microsoft 365 관리 센터에서 중앙 집중식 배포에 대해 자주 묻는 질문에 대 한 대답을 검토 합니다.
ms.openlocfilehash: 2d9a3c6f2cfe9418cc83cbd0f29537e5533c4257
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083565"
---
# <a name="centralized-deployment-faq"></a>중앙 집중식 배포 FAQ

조직이이 문서에 설명 된 대로 중앙 집중식 배포를 사용 하기 위한 모든 요구 사항을 충족 하는 경우 Office 365 관리자가 office 추가 기능 (Word, Excel, PowerPoint 및 Outlook)을 조직 내의 사용자 및 그룹에 배포 하는 것이 권장 되는 방법입니다.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>조직이 중앙 집중식 배포를 위해 설정 되었는지 어떻게 알 수 있나요?  

추가 기능의 중앙 집중식 배포에서는 사용자가 엔터프라이즈에 대해 Microsoft 365 앱을 사용 하 고 조직 로그인 자격 증명을 사용 하 여 Office에 로그인 하 고 Exchange Online 사서함이 있어야 합니다. 구독 디렉터리는 Azure Active Directory에 있거나 페더레이션 해야 합니다.  
 
온라인 사서함에 대해서만 중앙 집중식 배포가 지원 됩니다. 온-프레미스 Exchange 사서함에 대 한 배포는 지원 되지 않습니다.
 
[중앙 집중식 배포 호환성 검사](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   를 사용 하 여 구독에 대 한 자격이 있는지 확인할 수 있습니다. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>중앙 집중식 배포를 사용 하 여 추가 기능 사용자 지정을 대상으로 하는 방법은 무엇 인가요?  

중앙 집중식 배포에서는 개별 사용자, 그룹 및 테 넌 트의 모든 사용자에 대 한 할당을 지원 합니다. 중앙 집중식 배포는 최상위 그룹 또는 부모 그룹이 없는 그룹의 사용자에 게 사용 될 수 있지만, 중첩 된 그룹 또는 부모 그룹이 있는 그룹의 사용자에 게는 해당 되지 않습니다. 중앙 집중식 배포는 Office 365 그룹, 메일 그룹 및 보안 그룹과 같은 대부분의 Azure Active Directory 그룹에도 포함 됩니다.  

보다 쉬운 관리를 위해 개별 사용자 할당 대신 그룹 할당을 사용 하는 것이 좋습니다.
 
자세한 내용은 [사용자 및 그룹 할당](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)을 참조 하십시오.  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>모든 사용자에 대해 추가 기능을 표시 하는 데 소요 되는 시간  

모든 사용자에 대해 추가 기능을 표시 하는 데 최대 24 시간이 걸릴 수 있습니다. 추가 기능 업데이트에 대해 같은 시간을 사용 하거나, 설정 또는 해제에서 변경 되거나, 추가 기능이 제거 될 수 있습니다. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>관리자는 조직에 대 한 추가 기능에 대 한 사용자 액세스를 관리 하는 방법은 무엇 인가요?

사용자, 그룹 또는 전체 조직에 추가 기능을 쉽게 배포할 수 있도록 관리자에 게 중앙 집중식 배포를 사용 하는 것이 좋습니다.

사용자 액세스를 관리 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오. </br>[Outlook을 제외한 모든 클라이언트로부터 Office 스토어를 꺼서 추가 기능 다운로드를 금지](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) 하 고 </br>[Outlook 용 추가 기능을 설치 및 관리할 수 있는 관리자 및 사용자를 지정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN)합니다.

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>중앙 집중식 배포가 관리자에 게 Outlook 추가 기능에 대 한 배포 방법을 선택할 수 있는 유연성을 제공 하나요?  

예. 중앙 집중식 배포는 관리자가 추가 기능 배포 중 Outlook 추가 기능에 대 한 세 가지 배포 방법 중 하나를 선택할 수 있는 유연성을 제공 합니다.

**Fixed (기본값)**   추가 기능은 지정 된 사용자에 게 자동으로 배포 되며 제거할 수 없습니다.  
 
**사용 가능** 사용자는 관리자 관리 > 추가 기능 더 보기를 > 선택 하 여 Outlook에서 추가 기능을 설치할 수 있습니다.   
 
**선택 사항** 추가 기능은 할당 된 사용자에 게 자동으로 배포 되지만 제거할 수도 있습니다.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>관리자가 기간 업무 (LOB) 추가 기능을 업데이트할 수 있나요?  

예. 관리자가 새 매니페스트 파일을 업로드 하 여 관리자가 배포한 LOB 추가 기능의 메타 데이터 변경 내용을 지원할 수 있습니다. 다음에 Office 응용 프로그램이 시작 될 때 추가 기능이 업데이트 됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다.  
 
자세한 내용은 lob ( [기간 업무) 추가 기능](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins)을 참조 하십시오.  

## <a name="can-admins-turn-off-add-ins"></a>관리자가 추가 기능을 끌 수 있습니까?  

예. 관리자는 Microsoft 관리 센터에서 모든 사용자에 대해 배포 하는 추가 기능을 설정 하거나 해제할 수 있습니다.

자세한 내용은 [추가 기능 상태](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states)를 참조 하세요.  

##  <a name="can-admins-delete-or-remove-add-ins"></a>관리자가 추가 기능을 삭제 하거나 제거할 수 있나요?

예. 관리자는 Microsoft 관리 센터에서 모든 사용자에 대해 배포 된 추가 기능을 삭제할 수 있습니다.

자세한 내용은 [Delete the add in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in)을 참조 하십시오. 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>관리자가 중앙 집중식 배포를 사용 하 여 Office 스토어에서 유료 추가 기능을 배포할 수 있나요? 

아니요. 현재 중앙 집중식 배포를 사용 하 여 Office 스토어에서 유료 추가 기능을 배포할 수는 없습니다.  
 
매니페스트 파일이 나 URL을 요청 하기 위해 유료 추가 기능에 대 한 ISV 개발자에 게 전달 하는 것이 좋습니다. 그러면 테 넌 트 관리자가 중앙 집중식 배포를 사용 하 여 추가 기능을 LOB 추가 기능으로 배포할 수 있습니다.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>조직에 대 한 추가 기능을 관리 하는 데 필요한 관리자 역할은 무엇입니까?  

전역 관리자 역할을 사용 하 여 추가 기능을 관리 해야 합니다. Microsoft 365 for business 구독을 구매한 사용자는 전역 관리자입니다. 
 
구독에는 조직의 다른 사용자에 게 할당할 수 있는 관리자 역할 집합이 제공 됩니다. 각 관리자 역할은 일반 비즈니스 기능에 매핑되며 조직의 사용자에 게 Microsoft 365 관리 센터에서 특정 작업을 수행할 수 있는 권한을 부여 합니다.  
 
자세한 내용은 [관리자 역할 할당](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)을 참조 하십시오.  