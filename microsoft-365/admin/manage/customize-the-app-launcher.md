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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '앱 시작 관리자에 사용자 지정 타일을 추가 하 여 전자 메일, 문서, 앱, SharePoint 사이트, 외부 사이트 및 기타 리소스에 대 한 빠른 연결을 만듭니다. '
ms.openlocfilehash: 65c8da7aa0cdb68f4bf32a52b21140413a38a69a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361983"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>앱 시작 관리자에 사용자 지정 타일 추가

Office 365에서는 Office 365 시작 관리자를 사용하여 전자 메일, 일정, 문서, 앱을 쉽고 빠르게 열 수 있습니다([자세한 정보](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Office 365에서 제공되는 앱과 [SharePoint 스토어](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) 또는 [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)에서 추가한 사용자 지정 앱입니다.
  
앱 시작 관리자에 SharePoint 사이트, 외부 사이트, 레거시 앱 등을 가리키는 사용자 지정 타일을 추가할 수 있습니다. 사용자 지정 타일은 앱 시작 관리자의 **모든** 앱 아래에 표시 되지만,이를 **홈** 앱에 고정 하 고 사용자가 동일한 작업을 수행 하도록 지시할 수 있습니다. 이렇게 하면 작업을 수행 하기 위해 관련 사이트, 앱 및 리소스를 쉽게 찾을 수 있습니다. 아래 예제에서는 조직의 SharePoint 인트라넷 사이트에 액세스 하는 데 "Contoso Portal" 이라는 사용자 지정 타일을 사용 합니다. 
  
![Office 365 앱 시작 관리자](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>앱 시작 관리자에 사용자 지정 타일 추가

1. 관리 센터에서 **설정** > **설정** 으로 이동 하 여 **조직 프로필** 탭을 선택 합니다.
    
2. **조직 프로필** 탭에서 **사용자 지정 앱 시작 관리자 타일**을 선택 합니다.
  
3. **사용자 지정 타일 추가를**선택 합니다. 
  
4. 새 타일의 **타일 이름을** 입력 합니다. 이름이 타일에 표시됩니다. 
    
5. 타일에 대 한 **웹 사이트의 URL** 을 입력 합니다. 앱 시작 관리자에서 타일을 선택할 때 사용자가 이동 하도록 할 위치입니다. URL에 HTTPS를 사용 합니다.<br/>팁: SharePoint 사이트에 대 한 타일을 만드는 경우 해당 사이트로 이동 하 여 URL을 복사한 다음 여기에 붙여 넣습니다. 기본 팀 사이트의 URL은 다음과 같습니다.`https://<company_name>.sharepoint.com` 
  
6. 타일 **이미지의 URL** 을 입력 합니다. 이 이미지는 내 앱 페이지와 앱 시작 관리자에 표시 됩니다.<br/>팁: 이미지는 60x60 픽셀 이어야 하며, 인증을 요구 하지 않고 조직의 모든 사용자가 사용할 수 있어야 합니다.

7. 타일에 대 한 **설명을** 입력 합니다. 내 앱 페이지에서 타일을 선택 하 고 **앱 세부 정보**를 선택 하면이 표시 됩니다. 
  
8. **변경 내용 저장** 을 선택 하 여 사용자 지정 타일을 만듭니다. 
    
이제 사용자 지정 타일이 사용자의 **모든** 탭에 있는 앱 시작 관리자에 표시 됩니다. 
  
## <a name="promote-the-tile-to-app-launcher"></a>앱 시작 관리자에 게 타일 승격

1. 앱 시작 관리자 아이콘을 선택 하 고 **모든 앱**을 선택 합니다. 
    
2. 앱에 대 한 새 타일을 찾은 다음 줄임표를 선택 하 고 **시작 관리자에 고정**을 선택 합니다.
  
    > [!NOTE]
    > 이전 단계에서 만든 사용자 지정 타일이 보이지 않는 경우 Exchange Online 사서함이 사용자에 게 할당 되어 있고 사서함에 적어도 한 번 로그인 되어 있는지 확인 합니다. 이러한 단계는 Office 365의 사용자 지정 타일에 필요 합니다. 
  
> [!IMPORTANT]
> 사용자와 사용자는이 단계를 수행 하 여 내 앱 페이지에서 앱 시작 관리자에 게 지정 된 타일을 승격 해야 합니다. 
  
## <a name="edit-or-delete-a-custom-tile"></a>사용자 지정 타일 편집 또는 삭제

1. 관리 센터에서<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">조직 프로필</a> **설정** > 페이지로 이동 합니다.
    
2. **조직 프로필** 페이지에서 **조직의 사용자 지정 타일 추가**옆에 있는 **편집**을 선택 합니다.

3. 사용자 지정 타일의 **타일 이름**, **URL**, **설명**또는 **이미지 URL** 을 업데이트 합니다 ( [앱 시작 관리자에 사용자 지정 타일 추가](#add-a-custom-tile-to-the-app-launcher)참조).
    
4. **업데이트** \> **닫기를**선택 합니다. 
    
사용자 지정 타일을 삭제 하려면 **사용자 지정 타일** 창에서 타일을 선택 하 고 **타일** > **삭제**제거를 선택 합니다. 
  
## <a name="whats-next"></a>다음 작업

앱 시작 관리자에 타일을 추가 하는 것 외에도 앱 시작 관리자 타일을 Office 365 탐색 모음에 추가할 수 있습니다 ([자세한 정보](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). 조직의 브랜드에 맞게 Office 365의 모양과 느낌을 사용자 지정 하려면 [office 365 테마 사용자 지정](../setup/customize-your-organization-theme.md)을 참조 하세요.
  

