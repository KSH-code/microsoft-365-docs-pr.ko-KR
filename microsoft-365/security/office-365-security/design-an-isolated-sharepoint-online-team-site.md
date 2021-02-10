---
title: 격리된 SharePoint Online 팀 사이트 디자인
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 권한 수준 결정, 액세스 그룹이 있는 사용자에게 사용 권한 할당 및 중첩된 Azure AD 그룹을 포함하여 격리된 SharePoint Online 팀 사이트를 디자인합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f92a925948dbf6c8c5c1beb6b9c709f508c4b3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165514"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>격리된 SharePoint Online 팀 사이트 디자인

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


 **요약:** 격리된 SharePoint Online 팀 사이트에 대한 디자인 프로세스를 단계적으로 진행합니다.

이 문서에서는 격리된 SharePoint Online 팀 사이트를 만들기 전에 결정해야 하는 주요 디자인 결정을 내릴 수 있습니다.

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>1단계: SharePoint 그룹 및 사용 권한 수준 결정

기본적으로 모든 SharePoint Online 팀 사이트는 다음 SharePoint 그룹으로 만들어집니다.

- \<site name> 구성원

- \<site name> 방문자

- \<site name> 소유자

이러한 그룹은 Microsoft 365 및 Azure AD(Active Directory) 그룹과는 별개로, 사이트의 리소스에 대한 사용 권한을 할당하기 위한 기초입니다.

SharePoint 그룹의 구성원이 사이트에서 할 수 있는 작업을 결정하는 특정 권한 집합은 권한 수준입니다. SharePoint Online 팀 사이트에는 기본적으로 편집, 읽기 및 모든 권한의 세 가지 권한 수준이 있습니다. 다음 표에서는 SharePoint 그룹 및 할당된 사용 권한 수준의 기본 상관 관계에 대한 정보를 보여줍니다.

****

|SharePoint 그룹|사용 권한 수준|
|---|---|
|\<site name> 구성원|편집|
|\<site name> 방문자|읽기|
|\<site name> 소유자|모든 권한|
|

 **모범 사례:** 추가 SharePoint 그룹 및 권한 수준을 만들 수 있습니다. 그러나 격리된 SharePoint Online 사이트에 대해 기본 SharePoint 그룹 및 권한 수준을 사용하는 것이 좋습니다.

기본 SharePoint 그룹 및 권한 수준은 다음과 같습니다.

![SharePoint Online 사이트의 기본 SharePoint 그룹 및 권한 수준입니다.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>2단계: 액세스 그룹이 있는 사용자에게 사용 권한 할당

SharePoint 그룹에 사용자 계정 또는 사용자 계정이 구성원인 Microsoft 365 또는 Azure AD 그룹을 추가하여 사용자에게 권한을 할당할 수 있습니다. 추가된 사용자 계정에는 Microsoft 365 또는 Azure AD 그룹의 구성원 자격을 통해 직접 또는 간접적으로 SharePoint 그룹과 연결된 사용 권한 수준이 할당됩니다.

기본 SharePoint 그룹을 예로 들 수 있습니다.

- 사용자 계정과 그룹을 모두 포함할 수 있는 **\<site name> Members** SharePoint 그룹의 구성원에게는 편집 **권한** 수준이 할당됩니다.

- 사용자 계정과 그룹을 모두 포함할 수 있는 **\<site name> Visitors** SharePoint 그룹의 구성원에게는 읽기 **권한** 수준이 할당됩니다.

- 사용자 계정과 그룹을 모두 포함할 수 있는 **\<site name> Owners** SharePoint 그룹의 구성원에게는 모든 권한 **수준이** 할당됩니다.

 **모범 사례:** 개별 사용자 계정을 통해 사용 권한을 관리할 수 있는 경우 액세스 그룹으로 알려진 단일 Azure AD 그룹을 대신 사용하는 것이 좋습니다. 이렇게 하면 각 SharePoint 그룹의 사용자 계정 목록을 관리하는 대신 액세스 그룹의 구성원 자격을 통해 사용 권한 관리를 간소화할 수 있습니다.

Microsoft 365용 Azure AD 그룹은 서로 다른 Microsoft 365 그룹입니다. Azure AD 그룹은 유형이 보안으로 설정되어  있으며  전자 메일 주소가 없는 Microsoft 365 관리 센터에 표시됩니다. Azure AD 그룹은 다음 내에서 관리할 수 있습니다.

- AD DS(Active Directory 도메인 서비스)

    이러한 그룹은 프레미스 AD DS 인프라에서 만들어지며 Microsoft 365 구독과 동기화된 그룹입니다. Microsoft 365 관리 센터에서 이러한  그룹은 Active Directory와 동기화된 **상태입니다.**

- Office 365

    Microsoft 365 관리 센터, Azure Portal 또는 Microsoft PowerShell을 사용하여 만든 그룹입니다. Microsoft 365 관리 센터에서 이러한 그룹에는 클라우드 **상태가** **있습니다.**

 **모범 사례:** AD DS를 사용하고 Microsoft 365 구독과 동기화하는 경우 AD DS를 사용하여 사용자 및 그룹 관리를 수행하세요.

격리된 SharePoint Online 팀 사이트의 경우 권장되는 그룹 구조는 다음과 같습니다.

****

|SharePoint 그룹|Azure AD 기반 액세스 그룹|권한 수준|
|---|---|---|
|\<site name> 구성원|\<site name> 구성원|편집|
|\<site name> 방문자|\<site name> 뷰어|읽기|
|\<site name> 소유자|\<site name> 관리자|모든 권한|
|

 **모범 사례:** Microsoft 365 또는 Azure AD 그룹을 SharePoint 그룹의 구성원으로 사용할 수 있는 경우 Azure AD 그룹을 사용하는 것이 좋습니다. AD DS 또는 Microsoft 365를 통해 관리되는 Azure AD 그룹은 중첩된 그룹을 사용하여 권한을 할당할 수 있는 유연성을 제공합니다.

Azure AD 기반 액세스 그룹을 사용하도록 구성된 기본 SharePoint 그룹은 다음과 같습니다.

![액세스 그룹을 기본 SharePoint Online 사이트 그룹의 구성원으로 사용](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

세 가지 액세스 그룹을 디자인할 때 다음에 유의해야 합니다.

- **\<site name> Admins** 액세스 그룹에는 팀 사이트를 관리하는 소수의 SharePoint Online 관리자에 해당하는 구성원만 있을 수 있습니다.

- 대부분의 사이트 구성원은 구성원 **\<site name>** 또는 뷰어 **\<site name> 액세스 그룹에** 있습니다. 구성원 액세스 그룹의 **\<site name>** 사이트 구성원은 사이트의 리소스를 삭제하거나 수정할 수 있기 때문에 구성원 자격을 신중하게 고려해야 합니다. 의심스러우면 Viewers 액세스 그룹에 **\<site name> 사이트 구성원을** 추가합니다.

다음은 ProjectX라는 격리된 사이트에 대한 SharePoint 그룹 및 액세스 그룹의 예입니다.

![ProjectX라는 SharePoint Online 사이트에 액세스 그룹을 사용하는 예입니다.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>3단계: 중첩된 Azure AD 그룹 사용

소수의 사용자로 제한되는 프로젝트의 경우 사이트의 SharePoint 그룹에 추가된 단일 수준의 Azure AD 기반 액세스 그룹이 대부분의 시나리오에 적합합니다. 그러나 사용자가 많은 경우 이미 설정한 Azure AD 그룹의 구성원인 경우 중첩된 그룹 또는 다른 그룹을 구성원으로 포함하는 그룹을 사용하여 SharePoint 사용 권한을 보다 쉽게 할당할 수 있습니다.

예를 들어 영업, 마케팅, 엔지니어링, 법률 및 지원 부서의 임원과 임원 사용자 계정 멤버 자격이 있는 해당 부서의 임원들이 공동 작업을 위해 격리된 SharePoint 온라인 팀 사이트를 만들 수 있습니다. 새 사이트 구성원을 위한 새 그룹을 만들고 모든 개별 임원 사용자 계정을 해당 그룹에 배치하는 대신 각 부서의 기존 임원 그룹을 새 그룹에 배치합니다.

 여러 조직 간에 Microsoft 365 구독을 공유하는 경우 매우 많은 수의 사용자 계정으로 인해 조직에 대해 격리된 사이트에 대한 단일 수준의 그룹 구성원 자격을 관리하기 어려울 수 있습니다. 이 경우 조직 내의 그룹이 포함된 각 조직에 대해 중첩된 Azure AD 그룹을 사용하여 권한을 관리할 수 있습니다.

중첩된 Azure AD 그룹을 사용하세요.

1. 사용자 계정을 포함할 Azure AD 그룹을 식별하거나 만들고 적절한 사용자 계정을 구성원으로 추가합니다.

2. 다른 Azure AD 그룹을 포함할 컨테이너 Azure AD 기반 액세스 그룹을 만들고 해당 그룹을 구성원으로 추가합니다.

3. 컨테이너 액세스 그룹에 대한 적절한 액세스 수준에 대해 SharePoint 그룹 및 해당 사용 권한 수준을 식별합니다.

> [!NOTE]
> 중첩된 Microsoft 365 그룹은 사용할 수 없습니다.

ProjectX 구성원 액세스 그룹에 대한 중첩된 Azure AD 그룹의 예는 다음과 같습니다.

![ProjectX 사이트의 구성원 액세스 그룹에 중첩된 액세스 그룹을 사용하는 예입니다.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

리서치, 엔지니어링 및 프로젝트 잠재 고객 팀의 모든 사용자 계정은 사이트 구성원으로 고안된 것이기 때문에 Azure AD 그룹을 ProjectX 구성원 액세스 그룹에 더 쉽게 추가할 수 있습니다.

## <a name="next-step"></a>다음 단계

프로덕션에서 격리된 사이트를 만들고 구성할 준비가 되면 격리된 SharePoint Online 팀 사이트 배포를 [참조하세요.](deploy-an-isolated-sharepoint-online-team-site.md)

## <a name="see-also"></a>참고 항목

[격리된 SharePoint Online 팀 사이트](isolated-sharepoint-online-team-sites.md)

[격리된 SharePoint Online 팀 사이트 관리](manage-an-isolated-sharepoint-online-team-site.md)

[격리된 SharePoint Online 팀 사이트 배포](deploy-an-isolated-sharepoint-online-team-site.md)
