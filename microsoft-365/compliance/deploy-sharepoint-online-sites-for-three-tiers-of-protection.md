---
title: 3단계 보호를 위한 SharePoint Online 사이트 배포
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: '요약: 다양한 정보 보호 수준에 맞게 SharePoint Online 팀 사이트를 만들고 구성합니다.'
ms.openlocfilehash: 44aa7c126e3ac4b077868c055f35c0b99d678b58
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636136"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a>3단계 보호를 위한 SharePoint Online 사이트 배포

이 문서의 단계를 사용하여 초기, 중요 및 극비 SharePoint Online 팀 사이트를 디자인하고 배포합니다. 이러한 3계층 보호에 대한 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)를 참조하세요.
  
## <a name="baseline-sharepoint-online-team-sites"></a>초기 SharePoint Online 팀 사이트

초기 보호에는 공용 및 개인 팀 사이트가 모두 포함됩니다. 공용 팀 사이트는 조직의 모든 사용자가 검색하고 액세스할 수 있습니다. 개인 사이트는 팀 사이트와 연결된 Microsoft 365 그룹의 구성원만 검색하고 액세스할 수 있습니다. 이러한 유형의 팀 사이트 모두에서는 구성원이 다른 사용자와 사이트를 공유할 수 있습니다.
  
### <a name="public"></a>공개

공용 액세스 및 권한이 있는 초기 SharePoint Online 팀 사이트를 만들려면 다음 [지침](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)을 따릅니다.

구성 결과는 다음과 같습니다.
  
![공용 SharePoint Online 팀 사이트에 대한 기준 수준 보호입니다.](../media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a>비공개

개인 액세스 및 권한이 있는 초기 SharePoint Online 팀 사이트를 만들려면 다음 [지침](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)을 따릅니다.
  
구성 결과는 다음과 같습니다.
  
![개인 SharePoint Online 팀 사이트에 대한 기준 수준의 보호입니다.](../media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a>중요 SharePoint Online 팀 사이트

중요 SharePoint Online 팀 사이트는 개인 팀 사이트로 시작합니다.
  
먼저 다음 [지침](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)에 따라 개인 SharePoint Online 팀 사이트를 만듭니다.

다음으로, 새 SharePoint Online 팀 사이트에서 다음 단계를 사용하여 추가 권한 설정을 구성합니다.

1.  SharePoint 팀 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.
2.  **사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.
3.  **사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택하고 **저장**을 클릭합니다.

이러한 권한 설정의 결과는 다음과 같습니다.

- 구성원이 다른 구성원과 공유하는 기능은 사용할 수 없습니다.
- 구성원이 아닌 사용자가 액세스를 요청하는 기능은 사용할 수 있습니다.

구성 결과는 다음과 같습니다.
  
![격리된 SharePoint Online 팀 사이트에 대한 중요한 수준의 보호입니다.](../media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
사이트 구성원은 이제 액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 리소스에서 안전하게 공동 작업할 수 있습니다.
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a>극비 SharePoint Online 팀 사이트

극비 SharePoint Online 팀 사이트는 추가 권한 설정이 있는 개인 팀 사이트입니다.

먼저 다음 [지침](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)에 따라 개인 SharePoint Online 팀 사이트를 만듭니다.

다음으로, 새 SharePoint Online 팀 사이트에서 다음 단계를 사용하여 추가 권한 설정을 구성합니다.

1.  SharePoint 팀 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.
2.  **사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.
3.  **사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택합니다.
4. **액세스 요청 허용**을 해제한 다음, **저장**을 클릭합니다.

이러한 권한 설정의 결과는 다음과 같습니다.

- 구성원이 다른 구성원과 공유하는 기능은 사용할 수 없습니다.
- 구성원이 아닌 사용자가 액세스를 요청하는 기능은 사용할 수 없습니다.

구성 결과는 다음과 같습니다.
  
![격리된 SharePoint Online 팀 사이트에 대한 높은 기밀 수준의 보호입니다.](../media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
사이트 구성원은 이제 액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 리소스에서 안전하게 공동 작업할 수 있습니다.
  
## <a name="next-step"></a>다음 단계

[레이블 및 DLP를 사용하여 SharePoint Online 파일 보호](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a>참고 항목

[정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[클라우드 도입 및 하이브리드 솔루션](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
