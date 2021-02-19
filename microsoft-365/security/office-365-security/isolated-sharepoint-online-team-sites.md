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
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 사용, 요구 사항, 사용할 수 있는 기능을 포함하여 격리된 SharePoint Online 팀 사이트에 대해 알아봅니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286588"
---
# <a name="isolated-sharepoint-online-team-sites"></a>격리된 SharePoint Online 팀 사이트

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1](office-365-atp.md)
- SharePoint Online 

 **요약:** 격리된 SharePoint Online 팀 사이트의 용도에 대해 알아봅니다.

SharePoint Online 팀 사이트는 공동 작업 공간을 신속하게 만들 수 있는 손쉬운 방법입니다. Microsoft Office 365에서 노트, 문서, 기사, 일정 및 기타 리소스에 대해 함께 작업할 수 있습니다. SharePoint Online 팀 사이트는 Microsoft 365 그룹을 기준으로 하며, 그룹 구성원의 개인 집합이나 전체 조직과 오픈해서 공동 작업할 수 있도록 하는 간편한 관리 모델을 제공합니다. 기본 SharePoint Online 팀 사이트는 Office 365 그룹 구성원이 다른 사용자를 초대하고 사용 권한 설정을 제어할 수 있도록 합니다.

그러나 그룹 구성원에 의해 제어될 사이트 액세스와 SharePoint 관리자가 관리하는 SharePoint Online 사용 권한 수준이 필요한 경우가 간혹 있습니다. 이를 격리된 사이트라고 부르며, 이는 공동 작업, 콘텐츠 보기 또는 사이트를 관리하는 사용자 집합으로 격리됩니다. 다음에 대해 격리된 사이트가 필요할 수 있습니다.

- 조직 내의 비밀 프로젝트

- 조직에서 고도로 민감하거나 중요한 지적 재산권이 포함된 위치

- 조직이 수행했거나 조직을 대상으로 이행된 법적 조치에 대한 리소스

- 약간의 중복된 측면이 있지만 대부분이 별도 비즈니스 엔터티로 존재하는 여러 조직 사이에서 Microsoft 365 구독을 공유하려고 하는 경우

다음은 격리된 사이트에 대한 요구 사항입니다.

- SharePoint Online 관리자만 사이트 관리를 수행할 수 있습니다. 이러한 사이트 관리에는 사이트에 액세스하기 위한 그룹 구성원 자격과 사용자 지정 권한 구성이 포함됩니다.

- 사이트의 구성원은 팀 사이트에 다른 구성원을 초대할 수 없습니다.

- 격리된 사이트의 구성원이 아닌 사용자는 사이트에 대한 액세스를 요청할 수 없습니다. 해당 사이트와 연결된 모든 URL에 액세스하려고 하면 액세스 거부됨 웹 페이지가 수신됩니다.

SharePoint Online 관리자가 중앙 집중식 액세스 제어 및 사용자 지정 권한을 요구하면 시간이 지나면서 사이트가 격리되는 문제가 발생합니다. 예를 들어, 현재 구성원은 의도적으로나 실수로 사이트의 구성원이 아닌 Microsoft 365 구독 내의 다른 사용자를 초대하거나 해당 사용자에 대한 사용자 지정 권한을 구성할 수 없습니다.

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
