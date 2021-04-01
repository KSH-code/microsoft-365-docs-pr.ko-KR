---
title: 앱 시작 관리자에 사용자 지정 타일 추가
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '앱 시작커에 사용자 지정 타일을 추가하여 전자 메일, 문서, 앱, SharePoint 사이트, 외부 사이트 및 기타 리소스에 대한 빠른 링크를 만들 수 있습니다. '
ms.openlocfilehash: b6ae4deed1566492574e30cf8cb66a750c9858c8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470634"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>앱 시작 관리자에 사용자 지정 타일 추가

Microsoft 365에서는 앱 시작커를 사용하여 전자 메일, 일정, 문서 및 앱에 쉽고 빠르게 액세스 할 수 있습니다([자세한 내용은).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) SharePoint 스토어 또는 Azure AD에서 추가하는 사용자 지정 앱뿐만 [](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) 아니라 Microsoft 365에서 다운로드하는 [앱입니다.](/previous-versions/office/office-365-api/)
  
SharePoint 사이트, 외부 사이트, 레거시 앱 등을 가리키는 앱 시작 관리자에 사용자 지정 타일을 추가할 수 있습니다. 사용자 지정 타일은 앱 시작 사용자의 **모든** 앱 아래에 나타나지만  홈 앱에 고정하고 사용자에게 동일한 작업을 하게 지시할 수 있습니다. 이렇게 하면 작업을 할 관련 사이트, 앱 및 리소스를 쉽게 찾을 수 있습니다. 아래 예제에서는 "Contoso Portal"이라는 사용자 지정 타일을 사용하여 조직의 SharePoint 인트라넷 사이트에 액세스합니다. 
  
![앱 시작 프로그램](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>앱 시작러에 사용자 지정 타일 추가

1. 전역 관리자로 관리 센터에 로그인하고 설정 조직 설정으로 이동한 다음 조직  >  프로필 **탭을** 선택합니다.
    
2. 조직 **프로필 탭에서** 사용자 지정 **앱 시작 프로그램 타일 을 선택합니다.**
  
3. 사용자 **지정 타일 추가를 선택합니다.** 
  
4. 새 **타일의 타일** 이름을 입력합니다. 이름이 타일에 표시됩니다. 
    
5. 타일에 **대한 웹 사이트의 URL을** 입력합니다. 이 위치는 사용자가 앱 시작커에서 타일을 선택할 때 이동하려는 위치입니다. URL에 HTTPS를 사용합니다.<br/>팁: SharePoint 사이트에 대한 타일을 만드는 경우 해당 사이트로 이동하여 URL을 복사한 다음 여기에 붙여넣습니다. 기본 팀 사이트의 URL은 다음과 같습니다. `https://<company_name>.sharepoint.com` 
  
6. 타일 **이미지의 URL을** 입력합니다. 이미지가 내 앱 페이지 및 앱 시작커에 표시됩니다.<br/>팁: 이미지는 60x60 픽셀로, 인증을 요구하지 않고도 조직의 모든 사용자가 사용할 수 있습니다.

7. 타일에 **대한 설명을** 입력합니다. 내 앱 페이지에서 타일을 선택하고 앱 **세부** 정보를 선택하면 표시됩니다. 
  
8. 변경 **내용 저장을 선택하여** 사용자 지정 타일을 만들 수 있습니다. 
    
이제 사용자 지정 타일이 사용자와 사용자를  위해 모두 탭의 앱 시작커에 표시됩니다. 
  
## <a name="edit-or-delete-a-custom-tile"></a>사용자 지정 타일 편집 또는 삭제

1. 관리 센터에서 설정 조직 설정 조직 프로필  >    >  **탭으로** </a> 이동합니다.
    
2. 조직 **프로필 페이지의** 조직에 대한 사용자 지정 타일 추가 옆에 **있는** 편집 을 **선택합니다.**

3. 사용자 지정 **타일의 타일 이름,** **URL,** **설명** 또는 이미지 **URL을** 업데이트합니다(앱 시작에 사용자 지정 [타일 추가 참조).](#add-a-custom-tile-to-the-app-launcher)
    
4. 업데이트  \> **닫기 를 선택합니다.** 
    
사용자 지정 타일을 삭제하려면 사용자 지정 타일 창에서 타일을 선택하고 타일 **삭제를**   >  **선택합니다.** 
  
## <a name="whats-next"></a>다음 작업

앱 시작커에 타일을 추가하는 것 외에도 탐색 모음에 앱 시작 프로그램 타일을 추가할 수 있습니다([자세한 내용은).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) 조직의 브랜드에 맞게 Microsoft 365의 모양과 느낌을 사용자 지정하기 위해 Microsoft 365 테마 사용자 [지정을 참조합니다.](../setup/customize-your-organization-theme.md)
