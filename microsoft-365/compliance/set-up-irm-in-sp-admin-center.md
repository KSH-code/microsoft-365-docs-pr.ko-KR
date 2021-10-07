---
title: SharePoint 관리 센터의 IRM(정보 권한 관리) 설정
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: SharePoint RMS(권한 관리 서비스)를 통해 Microsoft Azure Active Directory 온라인 IRM을 사용하여 SharePoint 라이브러리를 보호하는 방법을 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f40977e453b228eddc745a6d29e3f5d119276abe
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170598"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>SharePoint 관리 센터의 IRM(정보 권한 관리) 설정

SharePoint Online에서 IRM 보호가 목록 및 라이브러리 수준의 파일에 적용됩니다. 조직에서 IRM 보호를 사용하기 전에 먼저 권한 관리를 설정해야 합니다. IRM은 Microsoft Azure Information Protection의 Microsoft Azure AD Rights Management 서비스에 의존하여 사용 제한을 암호화하고 할당합니다. 일부 Microsoft 365 계획에는 Azure 권한 관리가 포함되어 있지만 모두는 그렇지 않습니다. 자세한 내용은 Azure 권한 관리를 지원하는 Office 방법을 [읽어보아야 합니다.](/azure/information-protection/understand-explore/office-apps-services-support)
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>관리 센터에서 IRM SharePoint 켜기

조직에서 목록 및 SharePoint IRM으로 보호하려면 먼저 조직에 대한 권한 관리 서비스를 활성화해야 합니다. Azure 권한 관리 [활성화를 참조하세요.](/information-protection/deploy-use/activate-service) 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 권한 관리 서비스를 사용하도록 설정해야 합니다. 그렇지 않으면 Online에서 IRM 기능을 사용할 SharePoint 없습니다.
  
권한 관리 서비스를 활성화한 후 SharePoint 센터에 로그인하여 IRM을 켜야 합니다.
  
1. 전역 관리자 또는 관리자로 SharePoint 로그인합니다.
    
2. 앱 시작 프로그램 아이콘 앱 시작 프로그램 아이콘을 ![ Office 365.](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) 에서 왼쪽 위에 있는 **관리자를** 선택하고 관리자를 Microsoft 365 관리 센터. (관리 타일이 없는 경우 조직에 관리자 권한이 없습니다.) 
    
3. In the left pane, choose **Admin centers** \> **SharePoint.**
    
4. 왼쪽 창에서 설정 을 선택한 다음 클래식 설정 **페이지를 선택합니다.**
    
5. **IRM(정보** 권한 관리) 섹션에서 구성에 지정된 **IRM** 서비스 사용을 선택한 다음 새로 **고침 IRM** 설정. IRM 설정을 새로 고치면 조직의 사용자들이 자신의 목록 및 문서 라이브러리에서 IRM을 SharePoint 수 있습니다. 그러나 이 옵션을 표시하는 옵션은 라이브러리 라이브러리 및 목록 설정 1시간까지 설정.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>문서 라이브러리 및 SharePoint IRM 사용
<a name="__toc220831191"> </a>

IRM 설정을 새로 고치면 사이트 소유자가 목록 및 문서 SharePoint IRM을 보호할 수 있습니다. 자세한 내용은 목록 또는 라이브러리에 정보 권한 관리 [적용을 참조하세요.](apply-irm-to-a-list-or-library.md)
  
사이트 소유자가 목록 또는 라이브러리에 대해 IRM을 사용하도록 설정하면 해당 목록 또는 라이브러리에서 지원되는 모든 파일 형식을 보호할 수 있습니다. 라이브러리에 IRM을 사용하도록 설정하면 권한 관리가 해당 라이브러리의 모든 파일에 적용됩니다. 목록에 대해 IRM을 사용하도록 설정하면 실제 목록 항목이 아니라 목록 항목에 첨부된 파일에만 권한 관리가 적용됩니다.
  
사용자가 IRM 사용 목록 또는 라이브러리에서 파일을 다운로드하면 권한이 있는 사용자만 볼 수 있도록 파일이 암호화됩니다. 또한 각 권한 관리 파일에는 파일을 보는 사용자에 대한 제한을 적용하는 발행 라이선스가 포함되어 있습니다. 일반적인 제한 사항으로는 파일을 읽기 전용으로 설정하고, 텍스트 복사를 사용할 수 없습니다. 로컬 복사본을 저장하지 못하게 하며, 사용자가 파일을 인쇄할 수 없습니다. IRM 지원 파일 형식을 읽을 수 있는 클라이언트 프로그램은 권한 관리 파일 내의 발행 라이선스를 사용하여 이러한 제한을 적용합니다. 이는 권한 관리 파일이 다운로드된 후에도 보호를 유지하는 방식입니다. 목록 또는 라이브러리에서 IRM을 사용하도록 설정하려면 목록 또는 라이브러리에 정보 권한 관리 [적용을 참조하세요.](apply-irm-to-a-list-or-library.md)
  
브라우저에서는 IRM 사용 라이브러리의 문서를 만들거나 편집할 Office 없습니다. 대신 한 번씩 한 사람이 IRM으로 암호화된 파일을 다운로드하고 편집할 수 있습니다. 체크 인 및 체크 아웃을 사용하여 여러 사용자에 대해 공동 작성  *또는*  제작을 관리합니다. 
  
IRM으로 보호된 라이브러리에서 PDF 파일을 다운로드할 때 Microsoft 365 PDF 파일을 만듭니다. 파일의 확장명은 변경되지 않지만 파일이 보호됩니다. 이 파일을 보기 위해 Azure Information Protection 뷰어, 전체 Azure Information Protection 클라이언트 또는 보호된 PDF 파일 보기를 지원하는 다른 응용 프로그램이 필요합니다. 
  
SharePoint Online에서는 다음과 같은 파일 형식의 암호화가 지원됩니다.
  
- PDF
    
- Word, Excel 및 Microsoft Office 프로그램용 97-2003 파일 PowerPoint
    
- 다음 Office 프로그램, Word, Excel 및 PowerPoint 프로그램용 Open X Microsoft Office ML PowerPoint
    
- XPS(XML Paper Specification) 형식
 
> [!NOTE]
> 업로드 시 문서를 열 필요가 SharePoint 보호된 문서(예: 디지털 서명된 PDF 파일)에는 IRM 보호를 적용할 수 없습니다. 

## <a name="next-steps"></a>다음 단계
<a name="__toc220831191"> </a>

SharePoint Online에 대해 IRM을 사용하도록 설정한 후 목록 및 라이브러리에 권한 관리 적용을 시작할 수 있습니다. 자세한 내용은 목록 또는 라이브러리에 정보 [권한 관리 적용을 참조하세요.](apply-irm-to-a-list-or-library.md)
  
OneDrive 동기화 새 Windows 클라이언트는 이제 IRM으로 보호된 SharePoint 문서 라이브러리 및 OneDrive 위치(라이브러리에 대한 IRM 설정이 문서 액세스 권한 만료로 설정되지 않은 경우)를 동기화할 수 있습니다. 자세한 내용은 새 동기화 클라이언트 배포를 시작하거나 에 대한 새 OneDrive 동기화 클라이언트 [배포를 Windows.](/onedrive/deploy-on-windows)
  
[Top of page](set-up-irm-in-sp-admin-center.md)