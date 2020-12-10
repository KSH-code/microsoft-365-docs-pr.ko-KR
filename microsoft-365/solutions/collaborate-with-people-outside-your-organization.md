---
title: 조직 외부의 사용자와 공동 작업
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: 조직 외부의 사용자와 공동 작업을 위해 Teams, OneDrive 및 SharePoint와 같은 Microsoft 365 앱을 구성하는 방법을 학습합니다.
ms.openlocfilehash: 374ad8f5ec37fc0900fb38cb4e0f4743a02c4da4
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613457"
---
# <a name="collaborating-with-people-outside-your-organization"></a>조직 외부의 사용자와 공동 작업

Microsoft 365의 외부 공유 기능을 통해 조직의 사용자가 디렉터리에 계정이 없는 파트너, 공급업체, 고객 및 다른 사용자와 공동 작업을 할 수 있습니다. 전체 팀 또는 사이트를 조직 외부의 사용자나 개별 파일과 공유할 수 있습니다.

조직 외부의 사용자와의 공동 작업은 다음 두 가지 주요 구성 요소로 구성됩니다.

- **공유 사용** - 조직에 대해 원하는 공유 수준을 허용하도록 Azure Active Directory, Teams, Microsoft 365 그룹 및 SharePoint에서 공유 컨트롤을 구성합니다.
- **추가 보안** 사용 - 조직 외부의 사용자가 인증을 하도록 기본 공유 기능을 구성할 수 있는 반면, Microsoft 365는 외부에서 공유하는 동안 데이터를 보호하고 거버넌스 정책을 유지 관리하는 데 도움이 되는 다양한 추가 보안 및 규정 준수 기능을 제공합니다.

## <a name="enable-sharing"></a>공유 사용

기본적으로 Microsoft 365에서는 조직 외부의 사용자와의 공유가 SharePoint 및 OneDrive에서 사용되지만 Teams에서는 사용하지 않도록 설정됩니다. 많은 SharePoint 및 OneDrive 외부 공유 시나리오는 추가 구성 없이 작동됩니다. 사용 중인 시나리오의 설정을 확인하거나 새 설정을 사용하도록 설정하려면 다음 옵션 중 하나를 선택합니다.

- 문서 [공동](collaborate-on-documents.md) 작업 - 파일 및 폴더에서 조직 외부의 사용자(게스트 및 비인식 사용자)와의 공유 및 공동 작업을 허용하도록 Microsoft 365를 구성하는 방법을 학습합니다.
- [사이트에서 공동 작업](collaborate-in-site.md) - 게스트와 SharePoint 사이트를 공유하도록 Microsoft 365를 구성하는 방법을 학습합니다.
- [팀으로](collaborate-as-team.md) 공동 작업 - Teams에서 게스트 공동 작업을 사용하도록 Microsoft 365를 구성하는 방법을 학습합니다.

Microsoft 365에서 사용할 수 있는 게스트 공유 설정에 대한 포괄적인 내용은 [Microsoft 365](microsoft-365-guest-settings.md)게스트 공유 설정 참조를 참조하세요.

## <a name="enable-additional-security"></a>추가 보안 사용

조직 외부 사용자와 공유하는 데 사용할 시나리오를 사용하도록 설정한 후 추가 보호책을 고려하여 실수로 또는 의도적으로 부적절한 공유로부터 콘텐츠를 보호할 수 있습니다.

- [파일 및 폴더를](best-practices-anonymous-sharing.md) 공인되지 않은 사용자와 공유하기 위한 모범 사례 - 비인식 사용자와 공유하기 위한 모범 사례에 대해 자세히 알아보는 방법을 제공합니다.
- [우발적 노출](share-limit-accidental-exposure.md) 제한 - 조직 외부의 사용자와 실수로 중요한 콘텐츠를 공유하는 위험을 줄이는 방법을 배워야 합니다.
- [안전한](create-secure-guest-sharing-environment.md) 게스트 공유 환경 만들기 - 조직 외부의 사용자와의 공유가 안전하고 안전한 방식으로 수행되도록 지원하고 거버넌스 요구 사항을 충족하는 데 도움이 되도록 Microsoft 365에서 제공하는 도구에 대해 자세히 알아보습니다.

## <a name="collaborate-with-partner-companies"></a>파트너 회사와 공동 작업

다른 조직의 게스트가 많이 참여하는 대규모 프로젝트에서 작업하거나 게스트가 자주 변경되는 지속적인 공급업체 관계가 있는 경우 Azure Active Directory의 권한 관리를 사용하여 게스트 관리를 간소화하고 파트너 회사가 해당 책임에서 공유할 수 있도록 할 수 있습니다. 자세한 [내용은 관리되는 게스트가 있는 B2B 엑스트라넷](b2b-extranet.md) 만들기를 참조합니다.

## <a name="limit-sharing"></a>공유 제한

Microsoft 365의 공유 기능 중 일부가 거버넌스 정책과 충돌하는 경우 [Microsoft 365의](microsoft-365-limit-sharing.md) 공유 제한을 참조하여 공유 제한 옵션에 대해 자세히 알아보면 됩니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365의 파일 공동 작업 진행](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[Microsoft 365를 통해 SharePoint에서 파일 공동 작업 계획](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
