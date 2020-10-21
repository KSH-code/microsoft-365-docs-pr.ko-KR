---
title: 계획을 변경 하기 전에 데이터 백업
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Microsoft 365 요금제를 변경 하기 전에 Outlook, OneDrive, Yammer 및 SharePoint 콘텐츠를 백업 합니다.
ms.openlocfilehash: f74acee03a21f2dfdf01c10017346b81a2885b3b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647858"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Microsoft 365 for business 요금제를 전환 하기 전에 데이터 백업

사용자가 더 많은 데이터 관련 서비스를 사용 하는 다른 구독으로 전환 되는 경우 또는 사용자가 조직을 떠나는 경우 Microsoft 365에 저장 된 데이터의 복사본을 새 구독으로 전환 하기 전에 다운로드할 수 있습니다.

사용자를 같은 서비스가 있는 구독으로 이동 하는 경우에는 사용자 데이터를 백업할 필요가 없습니다. [다른 구독으로 사용자 이동을](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/move-users-different-subscription)참조 하세요.
  
## <a name="save-a-copy-of-outlook-information"></a>Outlook 정보 복사본 저장

사용자가 Outlook을 사용할 경우 요금제가 전환 되기 전에 [전자 메일, 연락처 및 일정을 outlook .pst 파일로 내보내거나 백업할](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) 수 있습니다.
  
새 요금제로 전환이 완료 되 면 사용자는 [Outlook .pst 파일에서 전자 메일, 연락처 및 일정을 가져올](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)수 있습니다.
  
## <a name="save-files-stored-in-onedrive-for-business"></a>비즈니스용 OneDrive에 저장 된 파일 저장

사용자는 다른 구독으로 전환 되기 전에 [OneDrive 또는 SharePoint에서 파일 및 폴더](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) 를 컴퓨터의 하드 드라이브에 있는 폴더 또는 조직의 네트워크에 있는 파일 공유와 같은 다른 위치에 다운로드할 수 있습니다.
  
## <a name="save-yammer-information"></a>Yammer 정보 저장

관리자는 모든 메시지, 메모, 파일, 항목, 사용자 및 그룹을 .zip 파일로 내보낼 수 있습니다. 자세한 내용은 [Yammer Enterprise에서 데이터 내보내기를](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)참조 하세요. 개발자는 [YAMMER API](https://go.microsoft.com/fwlink/p/?linkid=842495) 를 사용 하 여이 작업을 수행할 수 있습니다.
  
## <a name="how-to-save-sharepoint-information"></a>SharePoint 정보를 저장 하는 방법

사용자가 SharePoint Online을 포함 하는 구독에서이를 포함 하지 않는 가입으로 전환 되 면 해당 Microsoft 365 메뉴에 **sharepoint** 타일이 더 이상 표시 되지 않습니다.
  
그러나 새 구독이 전환 되는 조직과 같은 조직 내에 있는 한, 사용자는 여전히 SharePoint 팀 사이트에 액세스할 수 있습니다. 팀 사이트에 대 한 직접 URL을 사용 하 여 전자 필기장, 문서, 작업 및 일정을 보고 업데이트할 수 있습니다.
  
> [!TIP]
> 사용자가 구독을 전환 하기 전에 팀 사이트로 이동 하 여 브라우저에 URL을 즐겨찾기 또는 책갈피로 저장 하는 것이 좋습니다.
  
기본적으로 팀 웹 사이트의 URL은 다음과 같은 형식입니다.
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

여기서  _\<orgDomain\>_ 은 조직의 URL입니다.
  
예를 들어 조직의 도메인이 contoso.onmicrosoft.com 인 경우 팀 사이트의 직접 URL을 사용할 수 https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx 있습니다.
  
물론 사용자는 언제 든 지 SharePoint 팀 사이트에서 로컬 컴퓨터 또는 다른 위치로 SharePoint Online 문서를 다운로드할 수 있습니다.
