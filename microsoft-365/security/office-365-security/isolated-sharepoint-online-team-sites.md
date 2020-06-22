---
title: 격리된 SharePoint Online 팀 사이트
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 사용, 요구 사항, 사용할 수 있는 기능을 포함하여 격리된 SharePoint Online 팀 사이트에 대해 알아봅니다.
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819536"
---
# <a name="isolated-sharepoint-online-team-sites"></a>격리된 SharePoint Online 팀 사이트

 **요약:** 격리된 SharePoint Online 팀 사이트의 용도에 대해 알아봅니다.
  
SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.
  
However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:
  
- 조직 내의 비밀 프로젝트
    
- 조직에서 고도로 민감하거나 중요한 지적 재산권이 포함된 위치
    
- 조직이 수행했거나 조직을 대상으로 이행된 법적 조치에 대한 리소스
    
- 약간의 중복된 측면이 있지만 대부분이 별도 비즈니스 엔터티로 존재하는 여러 조직 사이에서 Microsoft 365 구독을 공유하려고 하는 경우
    
다음은 격리된 사이트에 대한 요구 사항입니다.
  
- SharePoint Online 관리자만 사이트 관리를 수행할 수 있습니다. 이러한 사이트 관리에는 사이트에 액세스하기 위한 그룹 구성원 자격과 사용자 지정 권한 구성이 포함됩니다.
    
- 사이트의 구성원은 팀 사이트에 다른 구성원을 초대할 수 없습니다.
    
- Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.
    
The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.
  
격리된 사이트를 다음과 같은 기타 기능과 함께 사용할 수 있습니다.
  
- 사이트의 리소스를 암호화 상태로 유지하는 정보 권한 관리. 이 기능이 로컬로 다운로드되거나 전체 조직에서 사용할 수 있는 다른 사이트로 업로드된 경우도 문제가 되지 않습니다.
    
- 사용자가 사이트의 리소스(예: 파일)를 전자 메일로 전송하지 못하게 하는 데이터 손실 방지
    
## <a name="next-steps"></a>다음 단계

평가판 구독에서 격리된 SharePoint Online 팀 사이트를 체험해보려면 [개발/테스트 환경에서 격리된 SharePoint Online 팀 사이트](isolated-sharepoint-online-team-site-dev-test-environment.md)의 단계별 지침을 참조하세요.
  
프로덕션 환경에 격리된 SharePoint Online 팀 사이트를 배포할 준비가 되면 [격리된 SharePoint Online 팀 사이트 디자인](design-an-isolated-sharepoint-online-team-site.md)에서 단계별 디자인 고려 사항을 참조하세요.
  
## <a name="related-topics"></a>관련 항목

[격리된 SharePoint Online 팀 사이트 디자인](design-an-isolated-sharepoint-online-team-site.md)
  
[격리된 SharePoint Online 팀 사이트 관리](manage-an-isolated-sharepoint-online-team-site.md)

[격리된 SharePoint Online 팀 사이트 배포](deploy-an-isolated-sharepoint-online-team-site.md)


