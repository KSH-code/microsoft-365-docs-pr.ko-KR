---
title: 보안 및 준수 센터에서 eDiscovery & 할당
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 보안 및 준수 센터를 사용하여 eDiscovery 관련 작업을 수행하는 데 & 할당합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d4be264791c4f3d37d7a88cb3d12d1023b3c347
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759892"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>보안 및 준수 센터에서 eDiscovery & 할당

사용자가 Office 365 또는 Microsoft 365 규정 준수 센터의 보안 & 준수 센터에서 [eDiscovery](ediscovery.md) 관련 도구를 사용하게 하려는 경우 적절한 사용 권한을 할당해야 합니다. 이 작업을 수행하는 가장 쉬운 방법은 보안 및 준수  센터의 사용 권한 페이지에서 해당 & 것입니다. 이 항목에서는 보안 및 준수 센터를 사용하여 eDiscovery 및 콘텐츠 검색 관련 작업을 수행하는 데 & 설명합니다.
  
Security & 준수 센터의 기본 eDiscovery 관련 역할 그룹을 **eDiscovery 관리자라고 합니다.** 이 역할 그룹 내에 두 개의 하위 그룹이 있습니다.
  
- **eDiscovery 관리자 - eDiscovery** 관리자는 보안 & 준수 센터의 콘텐츠 검색 도구를 사용하여 조직의 콘텐츠 위치를 검색하고 미리 보기 및 검색 결과 내보내기와 같은 다양한 검색 관련 작업을 수행할 수 있습니다. 또한 구성원은 Core eDiscovery 및 Advanced eDiscovery에서 사례를 만들고 관리하고, 사례에 구성원을 추가 및 제거하고, 케이스 보류를 만들고, 사례와 연결된 검색을 실행하고, 사례 데이터에 액세스할 수 있습니다. eDiscovery 관리자는 만든 사례에만 액세스하고 관리할 수 있습니다. 다른 eDiscovery 관리자가 만든 사례에 액세스하거나 관리할 수 없습니다.
  
- **eDiscovery 관리자** - eDiscovery 관리자는 eDiscovery 관리자 역할 그룹의 구성원으로, eDiscovery 관리자가 수행할 수 있는 동일한 콘텐츠 검색 및 사례 관리 관련 작업을 수행할 수 있습니다. 또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.
  
  - 보안 및 준수 센터의 **eDiscovery** 및 **고급 eDiscovery** 페이지에 & 액세스합니다.

  - 조직의 모든 경우에 대해 Advanced eDiscovery의 사례 데이터에 액세스합니다.
  
  - 자신을 사례의 구성원으로 추가한 후 eDiscovery 사례를 관리합니다.
  
  조직에서 eDiscovery 관리자(Administrator)를 원할 수 있는 이유는 추가 정보를 [참조하세요.](#more-information)

> [!NOTE]
> Advanced eDiscovery를 사용하여 사용자 데이터를 분석하려면 사용자(데이터의 보호자)에게 Office 365 E5 또는 Microsoft 365 E5 라이선스가 할당되어야 합니다. 또는 Office 365 E1 또는 Office 365 또는 Microsoft 365 E3 라이선스가 있는 사용자에게 Microsoft 365 E5 규정 준수 또는 Microsoft 365 eDiscovery 및 감사 추가 기능 라이선스가 할당될 수 있습니다. 사례에 구성원으로 할당되어 Advanced eDiscovery를 사용하여 데이터를 수집, 보기 및 분석하는 관리자, 규정 준수 담당자 또는 법률 담당자는 E5 라이선스가 필요하지 않습니다. Advanced eDiscovery 라이선스에 대한 자세한 내용은 [Advanced eDiscovery](get-started-with-advanced-ediscovery.md)시작을 참조하세요.
  
## <a name="confirm-your-roles"></a>역할 확인

- 조직 관리 역할 그룹의 구성원이거나 보안 및 준수 센터에서 eDiscovery 권한을 할당하려면 역할 관리 역할을 & 합니다.

- Security & Compliance Center PowerShell에서 [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) cmdlet을 사용하여 메일 사용이 가능한 보안 그룹을 eDiscovery 관리자 역할 그룹의 eDiscovery 관리자 하위 그룹 구성원으로 추가할 수 있습니다. 그러나 메일 사용이 가능한 보안 그룹을 eDiscovery Administrators 하위 그룹에 추가할 수 없습니다. 자세한 내용은 추가 [정보를 참조하십시오.](#more-information) 
  
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>보안 및 준수 센터에서 eDiscovery & 할당

1. [https://protection.office.com](https://protection.office.com)으로 이동합니다.
  
2. 회사 또는 학교 계정을 사용하여 로그인합니다.
  
3. 보안 및 준수 센터의 왼쪽 창에서 사용 권한을 선택하고 **eDiscovery** 관리자 옆에 있는 확인란을 선택합니다.
  
4. **eDiscovery 관리자** 플라이아웃 페이지에서 할당할 eDiscovery 권한에 따라 다음 중 하나를 선택합니다.
  
    **사용자를 eDiscovery 관리자로 설정:** **eDiscovery 관리자 옆에 있는** 편집을 **선택합니다.** **eDiscovery** 관리자 선택 섹션에서 **eDiscovery 관리자** 하이퍼링크 선택 하이퍼링크를 선택한 다음 아이콘 ![ 추가를 ](../media/ITPro-EAC-AddIcon.gif) **선택합니다.** eDiscovery 관리자로 추가할 사용자를 선택한 다음 추가를 **선택합니다.** 사용자 추가를 마치면 완료를 **선택합니다.** 그런 다음 편집 **eDiscovery** 관리자 플라이아웃  선택 페이지에서 저장을 선택하여 변경 내용을 eDiscovery 관리자 구성원에 저장합니다.
  
    **사용자를 eDiscovery 관리자로 설정:** **eDiscovery 관리자 옆에 있는** 편집을 **선택합니다.** **eDiscovery** 관리자 선택 섹션의 **eDiscovery** 관리자 아래에서 **eDiscovery** 관리자 선택, 편집을 선택한 다음 아이콘 추가를 ![ ](../media/ITPro-EAC-AddIcon.gif) **선택합니다.** **eDiscovery** 관리자로 추가할 사용자를 선택한 다음 **추가합니다.** 사용자 추가를 마치면 완료를 **선택합니다.** 그런 다음 편집 **eDiscovery** 관리자 플라이아웃  선택 페이지에서 저장을 선택하여 변경 내용을 eDiscovery 관리자 구성원에 저장합니다.
  
> [!NOTE]
> **Add-eDiscoveryCaseAdmin** cmdlet을 사용하여 사용자를 eDiscovery 관리자로 만들 수 있습니다. 그러나 이 cmdlet을 사용하여 사용자를 eDiscovery 관리자로 지정하려면 먼저 사용자에게 사례 관리 역할을 할당해야 합니다. 자세한 내용은 [Add-eDiscoveryCaseAdmin을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkID=798217) 
  
Security  & 준수 센터의 사용 권한 페이지에서 준수 관리자, 조직 관리 및 검토자 역할 그룹에 추가하여 사용자에게 eDiscovery 관련 권한을 할당할 수 있습니다. 이러한 각 역할 그룹에 할당된 eDiscovery 관련 RBAC 역할에 대한 설명은 [eDiscovery와 관련된 RBAC 역할을 참조하세요.](#rbac-roles-related-to-ediscovery)

## <a name="rbac-roles-related-to-ediscovery"></a>eDiscovery와 관련된 RBAC 역할

다음 표에는 Security & 준수 센터의 eDiscovery 관련 RBAC 역할이 나열되어 있으며 각 역할이 기본적으로 할당되는 기본 제공 역할 그룹을 나타냅니다.
  
| 역할 | 준수 관리자 | eDiscovery 관리자 & 관리자 | 조직 관리 | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|사례 관리 <br/> |![확인 표시](../media/checkmark.png) <br/> |![확인 표시](../media/checkmark.png) <br/> |![확인 표시](../media/checkmark.png) <br/> | <br/> |
|커뮤니케이션 <br/> | <br/> |![확인 표시](../media/checkmark.png) <br/> | <br/> | <br/> |
|규격 검색 <br/> |![확인 표시](../media/checkmark.png) <br/> |![확인 표시](../media/checkmark.png) <br/> |![확인 표시](../media/checkmark.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![확인 표시](../media/checkmark.png) <br/> | <br/> | <br/> |
|내보내기 <br/> | <br/> |![확인 표시](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![확인 표시](../media/checkmark.png) <br/> |![확인 표시](../media/checkmark.png) <br/> |![확인 표시](../media/checkmark.png) <br/> | <br/> |
|Preview <br/>  | <br/> |![확인 표시](../media/checkmark.png) <br/> | <br/> | <br/> |
|검토 <br/>  | <br/> |![확인 표시](../media/checkmark.png) <br/> | <br/> |![확인 표시](../media/checkmark.png) <br/> |
|RMS 암호 해독 <br/>  ||![확인 표시](../media/checkmark.png) <br/> |||
|검색 및 제거 <br/> | <br/> | <br/> |![확인 표시](../media/checkmark.png)           <br/> | <br/> |
||||
  
다음 섹션에서는 이전 표에 나열된 각 eDiscovery 관련 RBAC 역할에 대해 설명합니다.

### <a name="case-management"></a>사례 관리

이 역할을 사용하면 사용자가 보안 및 준수 센터에서 Core eDiscovery 및 Advanced eDiscovery 사례를 만들고, 편집하고, 삭제하고& 제어할 수 있습니다. 앞서 설명한 것 처럼 사용자에게 사례 관리 역할을 할당해야 **Add-eDiscoveryCaseAdmin** cmdlet을 사용하여 사용자를 eDiscovery 관리자로 만들 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [핵심 eDiscovery 시작](get-started-core-ediscovery.md)

- [Advanced eDiscovery 시작](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>커뮤니케이션

이 역할을 사용하면 고급 eDiscovery 사례에서 식별된 관리인과의 모든 통신을 관리할 수 있습니다. 여기에는 보류 알림 만들기, 보류 미리 알림 및 관리로의 에스컬레이터 만들기가 포함됩니다. 또한 사용자는 보유자 알림의 확인을 추적하고 각 보유자에서 보유자 포털에 대한 액세스를 관리하여 보유자로 식별된 사례에 대한 통신을 추적할 수 있습니다.

자세한 내용은 [Advanced eDiscovery의 통신 작업(Work with communications)을 참조하세요.](managing-custodian-communications.md)

### <a name="compliance-search"></a>규격 검색

이 역할을 사용하면 사용자가 보안 & 준수 센터에서 콘텐츠 검색 도구를 실행하여 사서함 및 공용 폴더, SharePoint Online 사이트, 비즈니스용 OneDrive 사이트, 비즈니스용 Skype 대화, Microsoft 365 그룹 및 Microsoft Teams 및 Yammer 그룹을 검색할 수 있습니다. 이 역할을 사용하면 검색 결과를 예상하고 내보내기 보고서를 만들 수 있지만 검색 결과 미리 보기, 내보내기 또는 삭제와 같은 콘텐츠 검색 작업을 시작하는 데는 추가 역할이 필요합니다.

준수 검색 역할이 할당되지만 미리 보기 역할이 없는 사용자는 미리 보기 역할이 할당된 사용자가 미리 보기 작업을 시작한 검색 결과를 미리 볼 수 있습니다. 미리 보기 역할이 없는 사용자는 초기 미리 보기 작업이 만들어진 후 최대 2주 동안 결과를 미리 볼 수 있습니다.

마찬가지로, 준수 검색 역할이 할당되지만 내보내기 역할이 없는 사용자는 내보내기 역할이 할당된 사용자가 내보내기 작업을 시작한 검색 결과를 다운로드할 수 있습니다. 내보내기 역할이 없는 사용자는 초기 내보내기 작업이 만들어진 후 최대 2주 동안 검색 결과를 다운로드할 수 있습니다. 그런 다음 내보내기 역할이 있는 사용자가 내보내기 작업을 다시 시작하지 않으면 결과를 다운로드할 수 없습니다.

자세한 내용은 [Office 365의 콘텐츠 검색을 참조하세요.](content-search.md)

### <a name="custodian"></a>Custodian

이 역할을 사용하면 고급 eDiscovery 사례의 보호자를 식별하고 관리할 수 있으며 Azure Active Directory 및 기타 원본의 정보를 사용하여 보호자와 연결된 데이터 원본을 찾을 수 있습니다. 사용자는 사서함, SharePoint 사이트 및 Teams와 같은 다른 데이터 원본을 사례의 보호자와 연결할 수 있습니다. 또한 사용자는 보유자와 연결된 데이터 원본에 법적 보존을 설정하여 사례의 컨텍스트에서 콘텐츠를 보존할 수 있습니다.

자세한 내용은 [Advanced eDiscovery의 보호자 작업(Work with custodians)을 참조하세요.](managing-custodians.md)

### <a name="export"></a>내보내기

이 역할을 사용하면 콘텐츠 검색 결과를 로컬 컴퓨터로 내보낼 수 있습니다. 또한 Advanced eDiscovery에서 분석을 위해 검색 결과를 준비할 수 있습니다.

검색 결과 내보내기에 대한 자세한 내용은 보안 및 준수 센터에서 검색 [결과 & 참조하세요.](export-search-results.md)

### <a name="hold"></a>Hold

이 역할을 사용하면 사용자가 사서함, 공용 폴더, 사이트, 비즈니스용 Skype 대화 및 Microsoft 365 그룹에 콘텐츠를 보류할 수 있습니다. 콘텐츠가 보류된 경우 콘텐츠 소유자는 원본 콘텐츠를 수정하거나 삭제할 수 있지만 보존이 제거되거나 보존 기간이 만료될 때까지 콘텐츠가 보존됩니다.

보류에 대한 자세한 내용은 다음을 참조하세요.

- [Core eDiscovery에서 보류 만들기](create-ediscovery-holds.md) 

- [Advanced eDiscovery에서 보류 만들기](add-custodians-to-case.md)

### <a name="preview"></a>Preview

이 역할을 사용하면 콘텐츠 검색에서 반환된 항목 목록을 볼 수 있습니다. 또한 목록에서 각 항목을 열고 보고 해당 콘텐츠를 볼 수 있습니다.

### <a name="review"></a>검토

이 역할을 사용하면 사용자가 [Advanced eDiscovery의 검토 집합에 액세스할 수 있습니다.](overview-ediscovery-20.md) 이 역할이 할당된 사용자는 Microsoft 365 규정 준수 센터의 **eDiscovery** > 고급 페이지에서 구성원으로 있는 사례 목록을 보고 열 수 있습니다. 사용자가 Advanced eDiscovery 사례에 액세스한 후  사례 데이터에 액세스할 검토 집합을 선택할 수 있습니다. 이 역할은 사용자가 사례와 연결된 컬렉션 검색 결과를 미리 보거나 다른 검색 또는 사례 관리 작업을 수행할 수 없습니다. 이 역할이 있는 사용자는 검토 집합의 데이터에만 액세스할 수 있습니다.

### <a name="rms-decrypt"></a>RMS 암호 해독

이 역할을 사용하면 검색 결과를 미리 볼 때 권한으로 보호된 전자 메일 메시지를 보고 암호 해독된 권한으로 보호된 전자 메일 메시지를 내보낼 수 있습니다. 또한 이 역할을 사용하면 암호화된 파일이 eDiscovery 검색 결과에 포함된 전자 메일 메시지에 첨부될 때 [Microsoft](encryption.md) 암호화 기술로 암호화된 파일을 보고 내보낼 수 있습니다. 또한 이 역할을 사용하면 고급 eDiscovery의 검토 집합에 추가된 암호화된 전자 메일 첨부 파일을 검토하고 쿼리할 수 있습니다. eDiscovery의 암호 해독에 대한 자세한 내용은 [Microsoft 365 eDiscovery](ediscovery-decryption.md)도구의 암호 해독을 참조하세요.

### <a name="search-and-purge"></a>검색 및 제거

이 역할을 사용하면 사용자가 콘텐츠 검색 조건과 일치하는 데이터를 대량으로 제거하는 작업을 수행할 수 있습니다. 자세한 내용은 조직에서 전자 메일 메시지 검색 및 삭제를 [참조하세요.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>추가 정보

- **eDiscovery 관리자를 만드는 이유** 앞에서 설명한 것처럼 eDiscovery 관리자는 조직의 모든 eDiscovery 사례를 보고 액세스할 수 있는 eDiscovery 관리자 역할 그룹의 구성원입니다. 모든 eDiscovery 사례에 액세스하는 이 기능에는 다음과 같은 두 가지 중요한 목적이 있습니다.

  - eDiscovery 사례의 유일한 구성원이 조직을 떠나면 조직 관리 역할 그룹의 구성원이나 eDiscovery 관리자 역할 그룹의 다른 구성원을 비롯한 어느 누구도 해당 eDiscovery 사례의 구성원이 아니므로 사례에 액세스할 수 없습니다. 이 상황에서는 해당 사례의 데이터에 액세스할 수 없습니다. 그러나 eDiscovery 관리자는 조직의 모든 eDiscovery 사례에 액세스할 수 있기 때문에 사례를 보고 자신을 또는 다른 eDiscovery 관리자를 사례의 구성원으로 추가할 수 있습니다.

  - eDiscovery 관리자는 모든 Core eDiscovery 및 Advanced eDiscovery 사례를 보고 액세스할 수 있기 때문에 모든 사례 및 관련 규정 준수 검색을 감사하고 조사할 수 있습니다. 이를 통해 규정 준수 검색 또는 eDiscovery 사례를 오용하는 것을 방지할 수 있습니다. 또한 eDiscovery 관리자는 준수 검색 결과에서 잠재적으로 중요한 정보에 액세스할 수 있기 때문에 eDiscovery 관리자인 사용자 수를 제한해야 합니다.

- **eDiscovery 관리자 역할 그룹의 구성원으로 그룹을 추가할 수 있나요?** 앞서 설명한처럼 보안 및 준수 센터 PowerShell의 **Add-RoleGroupMember** cmdlet을 사용하여 메일 사용이 가능한 보안 그룹을 eDiscovery 관리자 역할 그룹의 eDiscovery 관리자 하위 그룹의 구성원으로 추가할 수 & 있습니다. 예를 들어 다음 명령을 실행하여 메일 사용이 가능한 보안 그룹을 eDiscovery 관리자 역할 그룹에 추가할 수 있습니다. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange 메일 그룹 및 Microsoft 365 그룹은 지원되지 않습니다. 다음을 실행하여 Exchange Online PowerShell에서 만들 수 있는 메일 사용이 가능한 보안 그룹을 사용해야 `New-DistributionGroup -Type Security` 합니다. Exchange 관리 센터 또는 Microsoft 365 관리 센터에서 메일 사용이 가능한 보안 그룹을 만들고 구성원을 추가할 수도 있습니다. 새 메일 사용이 가능한 보안이 eDiscovery Managers 역할 그룹에 추가될 수 있도록 만든 후 최대 60분이 걸릴 수 있습니다. 

    또한 앞서 설명한 것 처럼 보안 및 준수 센터 PowerShell에서 **Add-eDiscoveryCaseAdmin** cmdlet을 사용하여 메일 사용이 가능한 보안 그룹을 eDiscovery 관리자로 & 수 없습니다. 개별 사용자만 eDiscovery 관리자로 추가할 수 있습니다.

    메일 사용이 가능한 보안 그룹을 사례의 구성원으로 추가할 수도 없습니다.
