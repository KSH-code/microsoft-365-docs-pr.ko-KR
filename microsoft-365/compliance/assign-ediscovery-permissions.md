---
title: 전자 메일 그룹에 eDiscovery 권한 Microsoft 365 규정 준수 센터
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: eDiscovery 관련 작업을 수행하는 데 필요한 사용 권한을 Microsoft 365 규정 준수 센터.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
ms.openlocfilehash: d6515dc213fe6b89a9a638c9df8dcad63785967c
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364558"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>전자 메일 그룹에 eDiscovery 권한 Microsoft 365 규정 준수 센터

사용자가 [eDiscovery](ediscovery.md) 관련 도구 중 원하는 도구를 Microsoft 365 규정 준수 센터 사용 권한을 할당해야 합니다. 이 작업을 수행하는 가장 쉬운 방법은 준수 센터의  사용 권한 페이지에서 해당 역할 그룹을 추가하는 것입니다. 이 항목에서는 eDiscovery 작업을 수행하는 데 필요한 사용 권한에 대해 설명합니다.
  
Microsoft 365 규정 준수 센터 주 eDiscovery 관련 역할 그룹을 **eDiscovery** 관리자라고 합니다. 이 역할 그룹 내에 두 개의 하위 그룹이 있습니다.
  
- **eDiscovery 관리자** - eDiscovery 관리자는 eDiscovery 검색 도구를 사용하여 조직의 콘텐츠 위치를 검색하고 미리 보기 및 검색 결과 내보내기 등의 다양한 검색 관련 작업을 수행할 수 있습니다. 또한 구성원은 Core eDiscovery 및 Advanced eDiscovery 사례를 만들고 관리하고, 사례에 구성원을 추가 및 제거하고, 사례 보류를 만들고, 사례와 연결된 검색을 실행하고, 사례 데이터에 액세스할 수 있습니다. eDiscovery Manager는 자신이 생성한 케이스에만 액세스하고 관리할 수 있습니다. 다른 eDiscovery Manager에서 생성한 케이스에 액세스하거나 관리할 수 없습니다.
  
- **eDiscovery 관리자** - eDiscovery 관리자는 eDiscovery 관리자 역할 그룹의 구성원으로, eDiscovery 관리자가 수행할 수 있는 동일한 콘텐츠 검색 및 사례 관리 관련 작업을 수행할 수 있습니다. 또한 eDiscovery 관리자는 다음과 같은 작업을 수행할 수 있습니다.
  
  - 페이지의 **Core eDiscovery** 및 Advanced eDiscovery **페이지에** 나열된 모든 사례에 Microsoft 365 규정 준수 센터.

  - Advanced eDiscovery에서 조직 내 모든 케이스의 케이스 데이터 액세스.
  
  - 케이스에 본인을 구성원으로 추가하고, eDiscovery 케이스 관리.
  
  - eDiscovery 사례에서 구성원을 제거합니다. eDiscovery 관리자만 사례에서 구성원을 제거할 수 있습니다. eDiscovery 관리자 하위 구성원인 사용자는 사용자가 사례를 만든 경우에도 사례에서 구성원을 제거할 수 없습니다.
  
  조직에서 eDiscovery 관리자(Administrator)를 원할 수 있는 이유는 추가 정보를 [참조하세요.](#more-information)

> [!NOTE]
> Advanced eDiscovery 사용하여 사용자의 데이터를 분석하려면 사용자(데이터 관리자)에게 Office 365 E5 또는 Microsoft 365 E5 할당해야 합니다. 또는 Office 365 E1 또는 Office 365 Microsoft 365 E3 라이선스가 있는 사용자에게 eDiscovery 및 Microsoft 365 E5 Compliance Microsoft 365 라이선스를 할당할 수 있습니다. 사례에 구성원으로 할당된 관리자, 규정 준수 관리자 또는 법률 Advanced eDiscovery 사용하여 데이터를 수집, 보기 및 분석하는 데 E5 라이선스가 필요하지 않습니다. 라이선스 라이선스에 Advanced eDiscovery 대한 자세한 내용은 에서 구독 [및 라이선싱을 Advanced eDiscovery.](overview-ediscovery-20.md#subscriptions-and-licensing)
  
## <a name="before-you-assign-permissions"></a>사용 권한을 할당하기 전에

- 조직 관리 역할 그룹의 구성원이거나 역할 관리 역할을 할당하여 조직에서 eDiscovery 권한을 할당해야 Microsoft 365 규정 준수 센터.

- Security & Compliance Center PowerShell에서 [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) cmdlet을 사용하여 메일 사용이 가능한 보안 그룹을 eDiscovery 관리자 역할 그룹의 eDiscovery 관리자 하위 그룹 구성원으로 추가할 수 있습니다. 그러나 메일 사용이 가능한 보안 그룹을 eDiscovery Administrators 하위 그룹에 추가할 수 없습니다. 자세한 내용은 추가 정보를 [참조하십시오.](#more-information)
  
## <a name="assign-ediscovery-permissions"></a>eDiscovery 사용 권한 할당

1. 으로 이동하여 권한을 할당할 수 있는 <https://compliance.microsoft.com> 계정을 사용하여 로그인합니다.
  
2. 왼쪽 창에서 사용 권한을 **선택합니다.**

3. 사용 권한 & **역할** 페이지의 준수 센터에서 역할을 **클릭합니다.** 

4. 준수 센터 **역할 페이지에서** **eDiscovery 관리자를 선택합니다.**
  
5. **eDiscovery 관리자** 플라이아웃 페이지에서 할당할 eDiscovery 권한에 따라 다음 중 하나를 선택합니다.
  
    **사용자를 eDiscovery 관리자로 설정:** **eDiscovery 관리자 옆에 있는** 편집 을 **선택합니다.** **eDiscovery** 관리자 선택 마법사 페이지에서 아이콘 ![ 추가를 클릭합니다.](../media/ITPro-EAC-AddIcon.gif) **추가** 합니다. eDiscovery 관리자로 추가할 사용자(또는 사용자)를 선택하고 추가 를 **선택합니다.** 사용자 추가를 마치면 완료 를 **선택합니다.** 그런 다음 편집 **eDiscovery** 관리자 선택 마법사 페이지에서 저장을 선택하여 eDiscovery 관리자 구성원에 대한 변경 내용을 저장합니다. 
  
    **사용자를 eDiscovery 관리자로 설정:** **eDiscovery 관리자 옆에 있는** 편집 **을 선택합니다.** **eDiscovery** 관리자 선택 페이지에서 아이콘 ![ 추가를 클릭합니다.](../media/ITPro-EAC-AddIcon.gif) **추가** 합니다. **eDiscovery 관리자(Administrator)로** 추가할 사용자를 선택한 다음 추가 **를 선택합니다.** 사용자 추가를 마치면 완료 를 **선택합니다.** 그런 다음 편집 **eDiscovery** 관리자 선택 마법사 페이지에서 저장을 선택하여 변경 내용을 eDiscovery 관리자 구성원에 저장합니다. 
  
> [!NOTE]
> **Add-eDiscoveryCaseAdmin** cmdlet을 사용하여 사용자를 eDiscovery 관리자로 만들 수 있습니다. 그러나 이 cmdlet을 사용하여 사용자에게 eDiscovery 관리자로 지정하려면 먼저 사용자에게 사례 관리 역할을 할당해야 합니다. 자세한 내용은 [Add-eDiscoveryCaseAdmin을 참조하세요.](/powershell/module/exchange/add-ediscoverycaseadmin) 
  
조직의  사용 권한 페이지에서 Microsoft 365 규정 준수 센터, 조직 관리 및 검토자 역할 그룹에 추가하여 사용자에게 eDiscovery 관련 권한을 할당할 수 있습니다. 이러한 각 역할 그룹에 할당된 eDiscovery 관련 RBAC 역할에 대한 설명은 [eDiscovery와 관련된 RBAC 역할을 참조하세요.](#rbac-roles-related-to-ediscovery)

## <a name="rbac-roles-related-to-ediscovery"></a>eDiscovery와 관련된 RBAC 역할

다음 표에는 Microsoft 365 규정 준수 센터 eDiscovery 관련 RBAC 역할이 나열되어 있으며 각 역할이 기본적으로 할당되는 기본 제공 역할 그룹을 나타냅니다.
  
| 역할 | 규정 준수 관리자 | eDiscovery 관리자 & 관리자 | 조직 관리 | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|사례 관리 <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> | <br/> |
|통신 <br/> | <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> | <br/> | <br/> |
|준수 검색 <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> | <br/> | <br/> |
|내보내기 <br/> | <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![확인 표시입니다.](../media/checkmark.png) <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> | <br/> |
|Preview <br/>  | <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> | <br/> | <br/> |
|검토 <br/>  | <br/> |![확인 표시입니다.](../media/checkmark.png) <br/> | <br/> |![확인 표시](../media/checkmark.png) <br/> |
|RMS 암호 해독 <br/>  ||![확인 표시](../media/checkmark.png) <br/> |||
|검색 및 제거 <br/> | <br/> | <br/> |![확인 표시](../media/checkmark.png)           <br/> | <br/> |
||||
  
다음 섹션에서는 이전 표에 나열된 각 eDiscovery 관련 RBAC 역할에 대해 설명합니다.

### <a name="case-management"></a>사례 관리

이 역할을 통해 사용자는 이 역할에서 Core eDiscovery 및 핵심 eDiscovery 및 Advanced eDiscovery 사례에 대한 액세스를 Microsoft 365 규정 준수 센터. 앞서 설명한처럼 **Add-eDiscoveryCaseAdmin** cmdlet을 사용하여 사용자를 eDiscovery 관리자로 지정하려면 먼저 사용자에게 사례 관리 역할을 할당해야 합니다.

자세한 내용은 다음을 참조하세요.

- [핵심 eDiscovery 시작](get-started-core-ediscovery.md)

- [고급 eDiscovery 시작](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>통신

이 역할을 사용하면 사용자가 사례에서 식별된 관리인과의 모든 통신을 Advanced eDiscovery 있습니다. 여기에는 보류 알림 만들기, 보류 미리 알림 및 관리로의 에스컬레이터가 포함됩니다. 또한 사용자는 보유자 확인을 추적하고 각 보유자에서 보유자 포털에 대한 액세스를 관리하여 보유자로 식별된 사례에 대한 통신을 추적할 수 있습니다.

자세한 내용은 [Work with communications in Advanced eDiscovery.](managing-custodian-communications.md)

### <a name="compliance-search"></a>준수 검색

이 역할을 사용하면 사용자가 사서함 및 공용 폴더 SharePoint, Microsoft 365 규정 준수 센터 온라인 사이트, 비즈니스용 OneDrive 사이트, 비즈니스용 Skype 대화, Microsoft 365 그룹을 검색할 수 있습니다. Microsoft Teams 및 Yammer 그룹입니다. 이 역할을 사용하면 검색 결과를 예상하고 내보내기 보고서를 만들 수 있지만 검색 결과 미리 보기, 내보내기 또는 삭제와 같은 콘텐츠 검색 작업을 시작하는 데는 다른 역할이 필요합니다.

콘텐츠 검색 및 Core eDiscovery에서 준수 검색 역할이 할당되지만 미리 보기 역할이 없는 사용자는 미리 보기 역할이 할당된 사용자가 미리 보기 작업을 시작한 검색 결과를 미리 볼 수 있습니다. 미리 보기 역할이 없는 사용자는 초기 미리 보기 작업이 만들어진 후 최대 2주 동안 결과를 미리 볼 수 있습니다.

마찬가지로, 콘텐츠 검색 및 Core eDiscovery에서 준수 검색 역할이 할당되지만 내보내기 역할이 없는 사용자는 내보내기 역할이 할당된 사용자가 내보내기 작업을 시작한 검색 결과를 다운로드할 수 있습니다. 내보내기 역할이 없는 사용자는 초기 내보내기 작업이 만들어진 후 최대 2주 동안 검색 결과를 다운로드할 수 있습니다. 그런 다음 내보내기 역할이 있는 사용자가 내보내기 작업을 다시 시작하지 않는 한 결과를 다운로드할 수 없습니다.

검색 결과를 미리 보고 내보내기 위한 2주 유예 기간(해당 검색 및 내보내기 역할 없이)은 검색 결과에 Advanced eDiscovery. 미리 보기 및 내보내기 역할을 사용자에게 할당해야 미리 보기 및 내보내기 역할이 Advanced eDiscovery.

### <a name="custodian"></a>Custodian

이 역할을 사용하면 사용자가 Advanced eDiscovery 보호자를 식별하고 관리할 수 있으며, Azure Active Directory 원본의 정보를 사용하여 보호자와 연결된 데이터 원본을 찾을 수 있습니다. 사용자는 사서함, SharePoint 사이트 등의 다른 데이터 원본을 Teams 수 있습니다. 또한 사용자는 보유자와 연결된 데이터 원본에 법적 보존을 설정하여 사례의 컨텍스트에서 콘텐츠를 보존할 수 있습니다.

자세한 내용은 [에서 보호자와 함께 작업하기를 Advanced eDiscovery.](managing-custodians.md)

### <a name="export"></a>내보내기

이 역할을 사용하면 콘텐츠 검색 결과를 로컬 컴퓨터로 내보낼 수 있습니다. 또한 검색 결과에서 분석을 위해 검색 결과를 준비할 Advanced eDiscovery.

검색 결과 내보내기에 대한 자세한 내용은 에서 검색 결과 내보내기 를 [Microsoft 365 규정 준수 센터.](export-search-results.md)

### <a name="hold"></a>Hold

이 역할을 사용하면 사용자가 사서함, 공용 폴더, 사이트, 비즈니스용 Skype 대화 및 Microsoft 365 배치할 수 있습니다. 콘텐츠가 보류된 경우에도 콘텐츠 소유자는 원래 콘텐츠를 수정하거나 삭제할 수 있지만, 해당 콘텐츠는 보류 상태가 제거되거나 보류 기간이 만료될 때까지 보존됩니다.

보류에 대한 자세한 내용은 다음을 참조하세요.

- [Core eDiscovery에서 보류 만들기](create-ediscovery-holds.md) 

- [보류를 Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Preview

이 역할을 사용하면 콘텐츠 검색에서 반환된 항목 목록을 볼 수 있습니다. 또한 목록에서 각 항목을 열고 보고 콘텐츠를 볼 수 있습니다.

### <a name="review"></a>검토

이 역할을 사용하면 사용자가 의 검토 집합에 액세스할 [Advanced eDiscovery.](overview-ediscovery-20.md) 이 역할이 할당된 사용자는 구성원으로 있는 페이지의 **eDiscovery** > 고급 페이지에서 사례 목록을 Microsoft 365 규정 준수 센터 수 있습니다. 사용자가 사례에 액세스한 Advanced eDiscovery 사례 데이터에 액세스하는 검토 집합을 선택할 수 있습니다.  이 역할은 사용자가 사례와 연결된 컬렉션 검색 결과를 미리 보거나 다른 검색 또는 사례 관리 작업을 수행할 수 없습니다. 이 역할이 있는 사용자는 검토 집합의 데이터에만 액세스할 수 있습니다.

### <a name="rms-decrypt"></a>RMS 암호 해독

이 역할을 사용하면 검색 결과를 미리 보고 권한으로 보호된 암호가 해독된 전자 메일 메시지를 내보낼 때 권한으로 보호된 전자 메일 메시지를 볼 수 있습니다. 또한 이 역할을 사용하면 암호화된 파일이 eDiscovery 검색 결과에 포함된 전자 메일 메시지에 첨부될 때 [Microsoft](encryption.md) 암호화 기술로 암호화된 파일을 보고 내보낼 수 있습니다. 또한 이 역할을 통해 사용자는 이 역할의 검토 집합에 추가된 암호화된 전자 메일 첨부 파일을 검토하고 쿼리할 Advanced eDiscovery. eDiscovery의 암호 해독에 대한 자세한 내용은 eDiscovery 도구에서 암호 [Microsoft 365 참조하세요.](ediscovery-decryption.md)

### <a name="search-and-purge"></a>검색 및 제거

이 역할을 사용하면 사용자가 콘텐츠 검색 조건과 일치하는 데이터를 대량으로 제거하는 작업을 수행할 수 있습니다. 자세한 내용은 조직에서 전자 메일 메시지 검색 및 [삭제를 참조하세요.](search-for-and-delete-messages-in-your-organization.md)

## <a name="adding-role-groups-as-members-of-ediscovery-cases"></a>eDiscovery 사례의 구성원으로 역할 그룹 추가

역할 그룹의 구성원이 할당된 사례에서 작업에 액세스하고 수행할 수 있도록 역할 그룹을 Core eDiscovery 및 Advanced eDiscovery 구성원으로 추가할 수 있습니다. 역할 그룹에 할당된 역할은 역할 그룹의 구성원이 할 수 있는 작업을 정의합니다. 그런 다음 역할 그룹을 사례의 구성원으로 추가하면 구성원이 특정 경우에 해당 작업에 액세스하고 수행할 수 있습니다. 역할 그룹을 사례의 구성원으로 추가하는 데 대한 자세한 내용은 다음을 참조하세요.

- [핵심 eDiscovery 시작](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

- [사례에서 구성원 Advanced eDiscovery 제거](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

이 점에 유의하여 역할 그룹에서 역할을 추가하거나 제거하면 역할 그룹이 구성원인 경우 해당 역할 그룹이 자동으로 제거됩니다. 이러한 이유는 사례의 구성원에게 추가 사용 권한을 부수적으로 제공하는 것을 방지하기 위한 것입니다. 마찬가지로 역할 그룹이 삭제되면 역할 그룹이 구성원이던 모든 경우에서 제거됩니다.

eDiscovery 사례의 구성원이 될 수 있는 역할 그룹에 역할을 추가하거나 제거하기 전에 Security [& Compliance PowerShell에서](/powershell/exchange/connect-to-scc-powershell) 다음 명령을 실행하여 역할 그룹이 구성원으로 있는 사례 목록을 얻을 수 있습니다. 역할 그룹을 업데이트한 후 역할 그룹을 해당 사례의 구성원으로 다시 추가합니다.

### <a name="get-a-list-of-core-ediscovery-cases-a-role-group-is-assigned-to"></a>역할 그룹이 할당된 Core eDiscovery 사례 목록 표시

```powershell
Get-ComplianceCase -RoleGroup "Name of role group"
```

### <a name="get-a-list-of-advanced-ediscovery-cases-a-role-group-is-assigned-to"></a>역할 그룹이 Advanced eDiscovery 사례 목록 표시

```powershell
Get-ComplianceCase -RoleGroup "Name of role group" -CaseType AdvancedEdiscovery
```

## <a name="more-information"></a>추가 정보

- **eDiscovery 관리자를 만드는 이유** 앞에서 설명한 것처럼 eDiscovery 관리자는 조직의 모든 eDiscovery 사례를 보고 액세스할 수 있는 eDiscovery 관리자 역할 그룹의 구성원입니다. 모든 eDiscovery 사례에 액세스하는 이 기능에는 다음과 같은 두 가지 중요한 목적이 있습니다.

  - eDiscovery 사례의 유일한 구성원이 조직을 떠나면 조직 관리 역할 그룹의 구성원이나 eDiscovery 관리자 역할 그룹의 다른 구성원을 비롯한 어느 누구도 해당 eDiscovery 사례의 구성원이 아니므로 사례에 액세스할 수 없습니다. 이 상황에서는 해당 사례의 데이터에 액세스할 수 없습니다. 그러나 eDiscovery 관리자는 조직의 모든 eDiscovery 사례에 액세스할 수 있기 때문에 사례를 보고 자신을 추가하거나 다른 eDiscovery 관리자를 사례의 구성원으로 추가할 수 있습니다.

  - eDiscovery 관리자는 모든 Core eDiscovery 및 Advanced eDiscovery 보고 액세스할 수 있기 때문에 모든 사례 및 관련 규정 준수 검색을 감사하고 Advanced eDiscovery 수 있습니다. 이렇게 하면 규정 준수 검색 또는 eDiscovery 사례를 오용하지 않도록 방지할 수 있습니다. 또한 eDiscovery 관리자는 준수 검색 결과에서 잠재적으로 중요한 정보에 액세스할 수 있기 때문에 eDiscovery 관리자인 사용자 수를 제한해야 합니다.

- **eDiscovery 관리자 역할 그룹의 구성원으로 그룹을 추가할 수 있나요?** 앞서 설명한 것 처럼 보안 및 준수 센터 PowerShell에서 **Add-RoleGroupMember** cmdlet을 사용하여 eDiscovery 관리자 역할 그룹의 eDiscovery 관리자 하위 그룹의 구성원으로 메일 사용이 가능한 보안 그룹을 추가할 수 & 있습니다. 예를 들어 다음 명령을 실행하여 메일 사용이 가능한 보안 그룹을 eDiscovery 관리자 역할 그룹에 추가할 수 있습니다. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange 그룹 및 Microsoft 365 그룹은 지원되지 않습니다. 를 실행하여 PowerShell에서 만들 수 있는 메일 사용이 가능한 Exchange Online 그룹을 사용해야 `New-DistributionGroup -Type Security` 합니다. 메일 사용이 가능한 보안 그룹을 만들고 구성원을 추가할 수도 Exchange 관리 센터 또는 [Microsoft 365 관리 센터.](https://go.microsoft.com/fwlink/p/?linkid=2024339) 새 메일 사용이 가능한 보안이 eDiscovery Managers 역할 그룹에 추가될 수 있도록 만든 후 최대 60분이 걸릴 수 있습니다. 

    또한 앞서 설명한 것 처럼 보안 및 준수 센터 PowerShell에서 **Add-eDiscoveryCaseAdmin** cmdlet을 사용하여 메일 사용이 가능한 보안 그룹을 eDiscovery 관리자로 & 수 없습니다. 개별 사용자만 eDiscovery 관리자로 추가할 수 있습니다.

    메일 사용이 가능한 보안 그룹을 사례의 구성원으로 추가할 수도 없습니다.
