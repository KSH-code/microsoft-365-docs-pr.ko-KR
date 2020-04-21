---
title: 조직 외부의 사용자와 공동 작업
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: 조직 외부의 사용자와 공동 작업용 Microsoft 365을 구성 하는 방법을 알아봅니다.
ms.openlocfilehash: 1b2a15312dcaacc398bb521f3ecfb6e7453f66bb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630728"
---
# <a name="collaborating-with-people-outside-your-organization"></a>조직 외부의 사용자와 공동 작업

Microsoft 365의 외부 공유 기능을 사용 하면 조직의 사용자가 파트너, 공급 업체, 고객 및 디렉터리에 계정이 없는 다른 사용자와 공동으로 작업할 수 있습니다. 전체 팀 또는 사이트를 조직 외부의 사용자 또는 개별 파일에 대해서만 공유할 수 있습니다.

조직 외부의 사용자와 공동 작업은 다음과 같은 두 가지 주요 구성 요소로 구성 됩니다.

- **공유 사용** -조직에 대해 원하는 공유 수준을 허용 하도록 Azure Active Directory, 팀, Microsoft 365 그룹 및 SharePoint에서 공유 컨트롤을 구성 합니다.
- **추가 보안 사용** -조직 외부 사용자가 인증을 받도록 기본 공유 기능을 구성할 수 있지만 Microsoft 365에서는 외부에서 데이터를 보호 하 고 거 버 넌 스 정책을 유지 관리 하는 데 도움이 되는 다양 한 추가 보안 및 규정 준수 기능을 제공 합니다.

## <a name="enable-sharing"></a>공유 사용

기본적으로 Microsoft 365에서 조직 외부의 사용자와 공유는 SharePoint 및 OneDrive에 대해 사용 하도록 설정 되지만 팀에는 사용할 수 없습니다. 많은 SharePoint 및 OneDrive 외부 공유 시나리오는 추가 구성 없이 작동 합니다. 사용 중인 시나리오에 대 한 설정을 확인 하거나 새로 사용 하도록 설정 하려면 다음 옵션 중 하나를 선택 합니다.

- [문서 공동 작업](collaborate-on-documents.md) -파일 및 폴더에서 조직 외부의 사용자 (게스트 및 인증 되지 않은 사용자 모두)와의 공유 및 공동 작업을 허용 하도록 Microsoft 365을 구성 하는 방법을 알아봅니다.
- [사이트에서 공동 작업](collaborate-in-site.md) -Microsoft 365을 구성 하 여 SharePoint 사이트와 게스트 공유를 사용 하도록 설정 하는 방법을 알아봅니다.
- [팀으로 공동 작업](collaborate-as-team.md) -팀에서 게스트 공동 작업을 사용 하도록 Microsoft 365을 구성 하는 방법을 알아봅니다.

Microsoft 365에서 제공 하는 게스트 공유 설정에 대 한 자세한 내용은 [microsoft 365 guest 공유 설정 참조](microsoft-365-guest-settings.md)를 참조 하세요.

## <a name="enable-additional-security"></a>추가 보안 사용

조직 외부의 사용자와 공유 하는 데 사용 하려는 시나리오를 사용 하도록 설정한 경우 실수로 또는 고의적인 부적절 한 공유 로부터 콘텐츠를 보호 하는 데 도움이 되는 추가 보호책을 고려해 야 합니다.

- [인증 되지 않은 사용자와 파일 및 폴더를 공유 하는 최상의 방법](best-practices-anonymous-sharing.md) -인증 되지 않은 사용자와의 공유 모범 사례에 대해 알아봅니다.
- [실수로 인 한 노출을 제한](share-limit-accidental-exposure.md) -실수로 중요 한 콘텐츠를 조직 외부의 사용자와 공유 하는 기회를 줄이는 방법을 알아봅니다.
- [보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md) -Microsoft 365에서 제공 하는 도구를 통해 조직 외부의 사용자와의 공유를 안전한 방식으로 수행 하 고 관리 요구 사항을 충족 하는지 확인할 수 있습니다.

## <a name="collaborate-with-partner-companies"></a>파트너 회사와 공동 작업

다른 조직의 여러 게스트가 포함 된 대규모 프로젝트에서 작업 하는 경우 또는 게스트에서 자주 변경 되는 공급 업체 관계가 있는 경우 Azure Active Directory에서 자격 관리를 사용 하 여 게스트 관리를 단순화 하 고 파트너 회사에서 해당 책임을 공유할 수 있습니다. 자세한 내용은 [관리 되는 게스트를 사용 하 여 B2B 엑스트라넷 만들기](b2b-extranet.md) 를 참조 하세요.

## <a name="limit-sharing"></a>제한 공유

Microsoft 365의 일부 공유 기능이 거 버 넌 스 정책과 충돌 하는 경우 공유 제한 옵션에 대 한 자세한 내용은 [microsoft 365의 공유 제한](microsoft-365-limit-sharing.md) 를 참조 하세요.

## <a name="see-also"></a>참고 항목

[Microsoft 365의 파일 공동 작업 소개](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[Microsoft 365을 사용 하 여 SharePoint의 파일 공동 작업 계획](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
