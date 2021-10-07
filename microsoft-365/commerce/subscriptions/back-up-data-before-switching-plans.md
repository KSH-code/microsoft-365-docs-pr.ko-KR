---
title: 계획을 변경하기 전에 데이터 백업
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: 계획 Outlook 변경하기 전에 OneDrive, Yammer 및 SharePoint 콘텐츠를 Microsoft 365 합니다.
ms.date: 03/17/2021
ms.openlocfilehash: c65c0ce533739f5d39314dc575d407d8d1af9ca8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171054"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>비즈니스용 요금제로 전환하기 Microsoft 365 데이터 백업

사용자가 데이터 관련 서비스가 적은 다른 구독으로 전환되거나 사용자가 조직을 떠나는 경우 새 구독으로 전환되기 전에 Microsoft 365 데이터 복사본을 다운로드할 수 있습니다.

서비스를 동일하거나 여러 개 있는 구독으로 사용자를 이동하는 경우 사용자 데이터를 백업할 필요가 없습니다. 다른 [구독으로 사용자 이동을 참조하세요.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>정보의 복사본 Outlook 저장

사용자가 Outlook 전환하기 전에 전자 메일, 연락처 및 일정을 [.pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) 파일로 Outlook 백업할 수 있습니다.
  
새 요금제로 전환이 완료되면 사용자는 [.pst](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)파일에서 전자 메일, 연락처 및 일정을 Outlook 수 있습니다.
  
## <a name="save-files-stored-in-onedrive-for-business"></a>파일에 저장된 파일을 비즈니스용 OneDrive

다른 구독으로 전환하기 전에 사용자는 [](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) 컴퓨터의 OneDrive 또는 SharePoint 폴더 또는 조직의 네트워크의 파일 공유와 같은 다른 위치로 파일 및 폴더를 다운로드할 수 있습니다.
  
## <a name="save-yammer-information"></a>사용자 Yammer 저장

관리자는 모든 메시지, 메모, 파일, 항목, 사용자 및 그룹을 .zip 있습니다. 자세한 내용은 에서 데이터 [내보내기 를 Yammer Enterprise.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) 개발자는 Yammer [API를](https://go.microsoft.com/fwlink/p/?linkid=842495) 사용하여 이 작업을 할 수 있습니다.
  
## <a name="how-to-save-sharepoint-information"></a>정보 저장 SharePoint 방법

사용자가 SharePoint Online이 있는 구독에서 없는 구독으로 전환된 경우 SharePoint 타일이 해당 Microsoft 365 메뉴에 나타나지 않습니다. 
  
그러나 새 구독이 전환된 구독과 동일한 조직 내에 있는 한 사용자는 여전히 SharePoint 팀 사이트에 액세스할 수 있습니다. 팀 사이트에 대한 직접 URL을 사용하여 전자 필기장, 문서, 작업 및 일정을 보고 업데이트할 수 있습니다.
  
> [!TIP]
> 구독이 전환되기 전에 사용자가 팀 사이트로 이동하여 URL을 브라우저에 즐겨찾기 또는 책갈피로 저장하는 것이 좋습니다.
  
기본적으로 팀 웹 사이트의 URL은 다음 형식입니다.
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

여기서  _\<orgDomain\>_ 은 조직의 URL입니다.
  
예를 들어 조직의 도메인이 contoso.onmicrosoft.com 팀 사이트의 직접 URL은 `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx` 입니다.
  
물론 사용자는 SharePoint 온라인 문서를 SharePoint 로컬 컴퓨터 또는 다른 위치로 다운로드할 수도 있습니다.
