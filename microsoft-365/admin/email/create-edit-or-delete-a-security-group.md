---
title: 보안 그룹에서 보안 그룹을 만들거나 편집하거나 Microsoft 365 관리 센터
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 보안 그룹을 만들거나 편집하거나 삭제하는 방법을 학습합니다.
ms.openlocfilehash: c2056996eb3954777654c5ea829379ecf005276a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184708"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>보안 그룹에서 보안 그룹을 만들거나 편집하거나 Microsoft 365 관리 센터

Microsoft 365 **그룹** 페이지에서 온라인 및 CRM Online에서 동일한 권한을 할당하는 데 사용할 수 있는 사용자 계정 SharePoint 있습니다. 예를 들어 관리자는 보안 그룹을 만들어 특정 사용자 그룹에 사이트 액세스 권한을 부여할 SharePoint 있습니다. 전역 관리자와 사용자 관리 관리자만 보안 그룹을 만들거나 편집하거나 삭제할 수 있는 권한이 있습니다. 관리자 역할에 대한 자세한 내용은 관리자 역할 [할당을 참조하세요.](../add-users/assign-admin-roles.md) 
  
전자 메일을 보내거나 사용자 그룹에 사용 권한을 할당하는 데 사용할 수 있는 [Exchange Online 및 SharePoint Online의 그룹](#groups-in-exchange-online-and-sharepoint-online), 그리고 사이트 및 사이트 모음에 대한 사용자 권한 및 액세스 권한을 부여하는 [Exchange Online 및 SharePoint Online의 그룹](#groups-in-exchange-online-and-sharepoint-online)도 있습니다. 
  
> [!IMPORTANT]
>  사이트 사서함을 사용할 계획이신가요? 개별적으로 추가되지 않고 보안 그룹을 통해 SharePoint 사이트에 추가되는 모든 사용자는 SharePoint를 통해서만 사이트 사서함을 사용할 수 있습니다. 이러한 사용자는 Outlook에서 사이트 사서함에 액세스할 수 없습니다. 자세한 내용은 [Use Microsoft 365 Groups instead of Site Mailboxes을 참조하십시오.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b) 
  
## <a name="manage-security-groups-in-the-admin-center"></a>관리 센터에서 보안 그룹 관리

### <a name="add-a-security-group"></a>보안 그룹 추가

1. 그룹 Microsoft 365 관리 센터 그룹 **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> 이동합니다.
  
2. 그룹 **페이지에서** 그룹 **추가를 선택합니다.**
    
3. 그룹 **유형 선택 페이지에서** 보안을 **선택합니다.** 
    
4. 단계에 따라 그룹 만들기를 완료합니다. 
 
### <a name="add-members-to-a-security-group"></a>보안 그룹에 구성원 추가
    
1. 그룹 페이지에서 보안 그룹  이름을 선택하고 구성원  탭에서 모두 보기 및 구성원 **관리를 선택합니다.** 
    
2. 그룹 창에서 구성원  추가를 선택하고 목록에서 해당 사람을 선택하거나 검색 상자에 추가할  사람의 이름을 입력한 다음 저장을 **선택합니다.**
    
    구성원을 제거하려면 이름 옆에 있는 X를 선택합니다. 
  
### <a name="edit-a-security-group"></a>보안 그룹 편집

1. 관리 센터에서 그룹 그룹  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">페이지로</a> 이동합니다.
  
2. 그룹 **페이지에서** 그룹의 이름을 선택합니다. 
    
3. 설정 창에서 일반 탭  또는 구성원  탭을 선택하여 그룹 세부 정보 또는 구성원을 편집합니다.

### <a name="delete-a-security-group"></a>보안 그룹 삭제

1. 관리 센터에서 그룹 그룹   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">페이지로</a> 이동합니다.
    
2. 그룹 **페이지에서** 그룹의 이름을 선택합니다. 
    
3. 그룹  삭제(와세트빈 아이콘)를 선택한 다음 삭제 를 선택하여 **확인을 선택합니다.**
    
    **그룹이** 삭제되면 닫기 를 선택합니다. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Exchange Online 및 SharePoint Online의 그룹

모든 사용자에게 동시에 전자 메일을 보낼 수 있도록 사용자 그룹을 만들 경우 관리 Exchange 받는 사람 그룹으로 Exchange  수 \>  \>  \> **있습니다.** 다음으로 **새** 추가를 선택하고 만들 그룹의 ![ ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) 종류를 선택합니다. 
  
- **메일 그룹**: 사용자 그룹에 메시지를 배포하는 데 사용됩니다. 메일 사용이 가능한 메일 그룹 또는 메일 *그룹이라고도 합니다.* 자세한 내용은 [메일 그룹 관리](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)를 참조하세요.
    
- **보안 그룹**: 사용자 그룹에 메시지를 배포하거나 리소스에 대한 액세스 권한을 부여하는 데 사용할 수 있습니다. 이 그룹을 메일 사용이 가능한 보안 *그룹이라고도 합니다.* 자세한 내용은 [메일 사용이 가능한 보안 그룹 관리](/Exchange/recipients/mail-enabled-security-groups)를 참조하십시오.
    
- **동적 메일 그룹**: 정의하는 필터 및 조건을 기반으로 메시지를 보낼 때마다 받는 사람 목록이 다시 계산되는 메일 그룹 유형입니다. 자세한 내용은 동적 메일 그룹 [관리를 참조하세요.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)
    
Exchange 관리 센터에서 메일 그룹 및 메일 사용이 가능한 보안 그룹을 만들면 해당 이름 및 사용자 목록이 보안 그룹 페이지에 **표시됩니다.** 두 위치에서 모두 이러한 그룹을 삭제할 수 있지만 편집은 Exchange 관리 센터에서만 가능합니다. 동적 메일 그룹이 보안 그룹 페이지에 **표시되지** 않습니다. 
  
 SharePoint 그룹은 사이트 모음을 만들 때 자동으로 만들어집니다. 기본 그룹은 SharePoint의 기본 사용 권한 수준(SharePoint 역할이라고도 함)을 통해 사용자 권한 및 액세스 권한을 부여합니다. 자세한 내용은 SharePoint Online의 기본 SharePoint [참조하세요.](/sharepoint/default-sharepoint-groups)
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>보안 그룹이 보안 그룹에서 만드는 보안 그룹과 어떻게 SharePoint?

보안 그룹은 보안 그룹, SharePoint, Exchange, MDM, Windows 사용할 수 있습니다. 사이트 모음에서 만든 SharePoint 해당 사이트 SharePoint 인식됩니다.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>조직을 안전하게 보호하기 위해 보안 그룹을 사용해야 하나요?

아니요. 이는 조직의 보안을 관리할 수 있는 한 가지 방법일 수 있습니다. 항상 사용자 권한 및 사이트에 대한 액세스 권한을 개별적으로 부여할 수 있습니다. 그러나 보안 그룹을 사용하면 더 큰 사용자 그룹을 쉽게 관리할 수 있습니다.
  
## <a name="can-i-send-email-to-a-security-group"></a>보안 그룹에 전자 메일을 보낼 수 있나요?

예. 그러나 전자 메일 및 공동 작업용 그룹을 사용하려는 경우 대신 그룹 Microsoft 365 [만드는](../create-groups/create-groups.md) 것이 좋습니다. 

## <a name="related-content"></a>관련 콘텐츠

[그룹에서](../create-groups/create-groups.md) 그룹 Microsoft 365 관리 센터(문서)\
[사용자에게 Microsoft 365](../create-groups/explain-groups-knowledge-worker.md) 설명(문서)\
[그룹 관리에서](../create-groups/manage-groups.md) Microsoft 365 관리 센터(문서)