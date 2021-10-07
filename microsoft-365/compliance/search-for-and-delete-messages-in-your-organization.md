---
title: 조직의 전자 메일 메시지 검색 및 삭제하기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Microsoft 365 규정 준수 센터의 검색 및 삭제하기 기능을 사용하여 조직의 모든 사서함에서 전자 메일 메시지를 검색하고 삭제할 수 있습니다.
ms.openlocfilehash: 33c65cb61be14d72631fd3a272b68f2dad2ffea6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204230"
---
# <a name="search-for-and-delete-email-messages"></a>전자 메일 메시지 검색 및 삭제

**이 문서는 관리자를 위해 작성되었습니다. 사서함에서 삭제할 항목을 찾으려고 하나요? [빠른 검색을 사용하여 메시지 또는 항목 찾기](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)** 를 참조하세요.

콘텐츠 검색 기능을 사용하여 조직의 모든 사서함에서 전자 메일 메시지를 검색하고 삭제할 수 있습니다. 이 방법은 다음과 같이 유해할 수 있거나 위험성이 높은 전자 메일을 제거하는 데 도움이 됩니다.

- 위험한 첨부 파일 또는 바이러스를 포함하는 메시지

- 피싱 메시지

- 중요한 데이터가 포함된 메시지

> [!CAUTION]
> 검색 및 삭제는 필요한 권한이 할당된 누구든지 조직의 사서함에서 전자 메일 메시지를 삭제할 수 있도록 하는 강력한 기능입니다.

## <a name="before-you-begin"></a>시작하기 전에

- 이 문서에 설명된 검색 및 제거 워크플로는 Microsoft Teams에서 채팅 메시지 또는 기타 콘텐츠를 삭제하지 않습니다. 2단계에서 만든 콘텐츠 검색이 Microsoft Teams의 항목을 반환하는 경우 3단계에서 항목을 제거할 때 해당 항목이 삭제되지 않습니다.

- 콘텐츠 검색을 만들고 실행하려면 **eDiscovery Manager** 역할 그룹의 구성원이거나 Microsoft 365 규정 준수 센터에서 **규정 준수 검색** 역할을 할당받아야 합니다. 메시지를 삭제하려면 **조직 관리** 역할 그룹의 구성원이거나 규정 준수 센터에서 **검색 및 제거** 역할을 할당받아야 합니다. 역할 그룹에 사용자를 추가하는 방법에 대한 자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.

  > [!NOTE]
  > **조직 관리** 역할 그룹은 Exchange Online과 Microsoft 365 규정 준수 센터 양측에 모두 있습니다. 이들은 서로 다른 권한을 부여하는 별도의 역할 그룹입니다. Exchange Online에서 **조직 관리** 의 구성원은 전자 메일 메시지를 삭제하는 데 필요한 권한을 부여하지 않습니다. 규정 준수 센터에서 **검색 및 삭제** 역할(직접 또는 **조직 관리** 등의 역할 그룹을 통해)이 할당되지 않은 경우 "A 매개 변수를 찾을 수 없습니다"라는 메시지와 함께 **New-ComplianceSearchAction** cmdlet을 실행하면 3단계에서 오류가 발생합니다.

- 메시지를 삭제하려면 보안 및 준수 센터 PowerShell을 사용해야 합니다. 연결하는 방법에 대한 자세한 내용은 [1단계](#step-1-connect-to-security--compliance-center-powershell)를 참조하세요.

- 사서함마다 한번에 최대 10개의 항목을 제거할 수 있습니다. 메시지를 검색하고 제거하는 기능은 사고 대응 도구로 고안되었으므로 이러한 제한은 사서함에서 메시지가 빠르게 제거되도록 합니다. 이 기능은 사용자 사서함을 정리하기 위한 기능이 아닙니다.

- 콘텐츠 검색에서 검색 및 삭제 작업을 사용하여 항목을 삭제할 수 있는 최대 사서함 수는 50,000개입니다. [2단계](#step-2-create-a-content-search-to-find-the-message-to-delete)에서 만든 검색에 50,000개를 초과하는 사서함이 있는 경우 3단계에서 만드는 삭제 작업이 실패합니다. 일반적으로 단일 검색에서 50,000개 이상의 편지함을 검색하는 작업은 조직의 모든 편지함을 포함하도록 검색을 구성할 때 발생할 수 있습니다. 이 제한은 50,000개 미만의 사서함에 검색 쿼리와 일치하는 항목이 포함된 경우에도 적용됩니다. 50,000개 이상의 사서함에서 검색 권한 필터를 사용하여 항목을 검색하고 제거하는 방법에 대한 지침은 [자세한 정보](#more-information) 색션을 참조하세요.

- 이 문서의 절차는 Exchange Online 사서함 및 공용 폴더에서 항목을 삭제하는 데에만 사용할 수 있습니다. SharePoint 또는 비즈니스용 OneDrive 사이트에서 콘텐츠를 삭제하는 데에는 사용할 수 없습니다.

- Advanced eDiscovery 사례에서 검토 집합의 전자 메일 항목은 이 문서의 절차를 사용하여 삭제할 수 없습니다. 검토 집합의 항목이 실제 서비스가 아닌 Azure Storage 위치에 저장되기 때문입니다. 즉, 1단계에서 만든 콘텐츠 검색에서 이를 반환하지 않습니다. 검토 집합의 항목을 삭제하려면 검토 집합이 포함된 Advanced eDiscovery 사례를 삭제해야 합니다. 자세한 내용은 [Advanced eDiscovery 사례 닫기 또는 삭제하기](close-or-delete-case.md)를 참조하세요.

## <a name="step-1-connect-to-security--compliance-center-powershell"></a>1단계: 보안 및 준수 센터 PowerShell에 연결

첫 번째 단계에서는 조직의 보안 및 준수 센터 PowerShell에 연결합니다. 단계별 지침은 [보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell)를 참조하세요.

## <a name="step-2-create-a-content-search-to-find-the-message-to-delete"></a>2단계: 삭제할 메시지를 찾는 콘텐츠 검색 만들기

두 번째 단계는 콘텐츠 검색을 만들고 실행하여 조직의 사서함에서 제거하려는 메시지를 찾는 것입니다. Microsoft 365 규정 준수 센터를 사용하거나 Security & Compliance PowerShell에서 **New-ComplianceSearch** 및 **Start-ComplianceSearch** cmdlet을 실행하여 검색을 만들 수 있습니다. 이 검색에 대한 쿼리와 일치하는 메시지는 [3단계](#step-3-delete-the-message)에서 **New-ComplianceSearchAction -Purge** 명령을 실행하여 삭제됩니다. 콘텐츠 검색 생성 및 검색 쿼리 구성에 대한 자세한 내용은 다음 항목을 참조하세요.

- [Office 365의 콘텐츠 검색](content-search.md)

- [콘텐츠 검색에 대한 키워드 쿼리](keyword-queries-and-search-conditions.md)

- [New-ComplianceSearch](/powershell/module/exchange/New-ComplianceSearch)

- [Start-ComplianceSearch](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> 이 단계에서 만드는 콘텐츠 검색에서 검색되는 콘텐츠 위치에는 SharePoint 또는 비즈니스용 OneDrive 사이트가 포함될 수 없습니다. 전자 메일 메시지에 사용되는 콘텐츠 검색에는 사서함 및 공용 폴더만 포함될 수 있습니다. 콘텐츠 검색에 사이트가 포함되는 경우 **New-ComplianceSearchAction** cmdlet을 실행할 때 3단계에서 오류가 발생합니다.

### <a name="tips-for-finding-messages-to-remove"></a>제거할 메시지를 찾기 위한 팁

검색 쿼리의 목적은 검색의 결과 범위를 제거할 메시지로만 좁히는 것입니다. 다음 팁을 참조하세요.

- 메시지의 제목 줄에 사용된 정확한 텍스트나 구를 알고 있으면 검색 쿼리에 **Subject** 속성을 사용합니다.

- 메시지의 정확한 날짜(또는 날짜 범위)를 알고 있으면 검색 쿼리에 **Received** 속성을 포함합니다.

- 메시지를 보낸 사람을 알고 있으면 검색 쿼리에 **From** 속성을 포함합니다.

- 검색 결과를 미리 확인하여 콘텐츠 검색이 삭제하려는 메시지만 반환하는지 검토합니다.

- 검색 예상 통계(Microsoft 365 규정 준수 센터의 검색 세부 정보 창에 표시되거나 [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch) cmdlet을 사용할 경우에 표시)를 사용하여 결과의 총 개수를 가져올 수 있습니다.

다음은 의심스러운 전자 메일 메시지를 찾는 쿼리의 두 가지 예입니다.

- 이 쿼리는 2016년 4월 13일과 2016년 4월 14일 사이에 사용자가 받은 메시지 중에서 제목 줄에 "action" 및 "required"가 포함된 메시지를 반환합니다.

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- 이 쿼리는 chatsuwloginsset12345@outlook.com에서 보낸 메시지 중에서 제목 줄에 "Update your account information"이 포함된 메시지를 반환합니다.

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

다음은 사용할 쿼리를 만들고 **New-ComplianceSearch** 및 **Start-ComplianceSearch** cmdlet을 실행하여 검색을 시작하고 조직의 모든 사서함을 검색하는 예제입니다.

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-3-delete-the-message"></a>3단계: 메시지 삭제

제거할 메시지를 반환하도록 콘텐츠 검색을 만들고 구체화한 후 마지막 단계는 보안 및 준수 PowerShell에서 **New-ComplianceSearchAction -Purge** 명령을 실행하여 메시지를 삭제하는 것입니다. 메시지를 일시 또는 영구 삭제할 수 있습니다. 일시 삭제된 메시지는 사용자의 복구 가능한 항목 폴더로 이동하고 삭제된 항목 보존 기간이 만료될 때까지 보존됩니다. 영구 삭제된 메시지는 사서함에서 영구 제거 표시되고 관리되는 폴더 도우미에서 다음에 사서함을 처리할 때 영구적으로 제거됩니다. 사서함에 대해 단일 항목 복구를 사용하는 경우 삭제된 항목 보존 기간이 만료되면 영구 삭제된 항목은 영구히 제거됩니다. 사서함이 보류 중인 경우 항목에 대한 보존 기간이 만료되거나 사서함에서 보류가 제거될 때까지 삭제된 메시지가 보존됩니다.

> [!NOTE]
> 앞서 설명한 대로 콘텐츠 검색에서 반환되는 Microsoft Teams의 항목은 **New-ComplianceSearchAction -Purge** 명령을 실행할 때 삭제되지 않습니다.

다음 명령을 실행하여 메시지를 삭제하려면 [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)되어 있는지 확인하세요.

### <a name="soft-delete-messages"></a>일시 삭제 메시지

다음 예에서 명령은 “피싱 메시지 제거”라는 콘텐츠 검색에 의해 반환된 검색 결과를 일시 삭제합니다.

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

### <a name="hard-delete-messages"></a>메시지 영구 삭제

"피싱 메시지 제거" 콘텐츠 검색에서 반환되는 항목을 영구 삭제하려면 다음 명령을 실행합니다.

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

이전 명령을 실행하여 메시지를 일시 삭제하거나 영구 삭제하는 경우 *SearchName* 매개 변수에 지정된 검색은 1단계에서 만든 콘텐츠 검색입니다.

자세한 내용은 [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction)을 참조하세요.

## <a name="more-information"></a>추가 정보

- **검색 및 삭제 작업에 대한 상태를 어떻게 가져오나요?**

  **Get-ComplianceSearchAction** 을 실행하여 삭제 작업의 상태를 가져옵니다. **New-ComplianceSearchAction** cmdlet을 실행할 때 생성되는 개체의 이름은 `<name of Content Search>_Purge` 형식을 사용하여 지정됩니다.

- **메시지를 삭제하면 어떻게 되나요?**

  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 명령을 사용하여 삭제한 메시지는 제거 폴더로 이동되고 사용자가 액세스할 수 없습니다. 사서함에서 단일 항목 복구를 사용하는 경우 메시지는 제거 폴더로 이동된 후 삭제된 항목 보존 기간 동안 보존됩니다. Microsoft 365에서는 새 사서함을 만들 때 단일 항목 복구가 기본적으로 사용됩니다. 삭제된 항목 보존 기간이 만료되면 메시지는 영구 삭제로 표시되고 관리되는 폴더 도우미에서 다음에 사서함을 처리할 때 Microsoft 365에서 제거됩니다.

  `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` 명령을 사용하면 메시지가 사용자의 복구 가능한 항목 폴더에 있는 삭제 폴더로 이동됩니다. Microsoft 365에서 즉시 제거되지 않습니다. 사용자는 사서함에 대해 구성된 삭제된 항목 보존 기간을 기반으로 하는 기간 동안 지운 편지함 폴더의 메시지를 복구할 수 있습니다. 이 보존 기간이 만료된 후(또는 사용자가 만료되기 전에 메시지를 제거한 경우) 메시지는 Purges 폴더로 이동되고 사용자가 더 이상 액세스할 수 없습니다. 삭제 폴더에 있으면 사서함에 대해 단일 항목 복구가 활성화된 경우 사서함에 대해 구성된 삭제된 항목 보존 기간에 따라 메시지가 보존됩니다. (Microsoft 365에서는 새 사서함을 만들 때 기본적으로 단일 항목 복구가 활성화됩니다.) 삭제된 항목 보존 기간이 만료된 후 메시지는 영구 삭제로 표시되고 다음에 관리되는 폴더 도우미에서 사서함이 처리될 때 Microsoft 365에서 제거됩니다.

- **50,000개를 초과하는 사서함에서 메시지를 삭제해야 하는 경우 어떻게 되나요?**

  앞서 설명한 대로 최대 50,000개의 사서함에서 검색 및 삭제 작업을 수행할 수 있습니다(50,000개 미만의 항목에 검색 쿼리와 일치하는 항목이 포함된 경우에도 마찬가지입니다.) 50,000개를 초과하는 사서함에서 검색 및 삭제 작업을 수행해야 하는 경우 검색되는 사서함 수를 50,000개 이하로 줄여주는 임시 검색 권한 필터를 만들어 보세요. 예를 들어 여러 부서, 주 또는 국가에 조직의 사서함이 포함되어 있는 경우 이러한 사서함 속성 중 하나를 기반으로 사서함 검색 권한 필터를 만들어 조직의 사서함 하위 집합을 검색할 수 있습니다. 검색 사용 권한 필터를 만든 후 1단계에서 설명한 대로 검색을 만든 후 3단계에서 설명한 대로 메시지를 삭제합니다. 그런 다음 필터를 편집하여 다른 사서함 집합에서 메시지를 검색한 후 삭제할 수 있습니다. 검색 권한 필터를 만드는 방법에 대한 자세한 내용은 [콘텐츠 검색에 대한 권한 필터링 구성](permissions-filtering-for-content-search.md)을 참조하세요.

- **검색 결과에 포함된 인덱싱되지 않은 항목이 삭제되나요?**

  아니요. `New-ComplianceSearchAction -Purge 명령은 인덱싱되지 않은 항목을 삭제하지 않습니다.

- **원본 위치 유지 또는 소송 보존에 포함되거나 Microsoft 365 보존 정책에 할당된 사서함에서 메시지를 삭제하면 어떻게 되나요?**

  메시지가 제거되고 제거 폴더로 이동된 후에는 보존 기간이 만료될 때까지 메시지가 보존됩니다. 보존 기간이 무제한이면 보존가 제거되거나 보존 기간이 변경 될 때까지 항목이 보존됩니다.

- **다양한 보안 및 준수 센터 역할 그룹 간에 검색 및 제거 워크플로가 분리되어 있는 이유**

  앞에서 설명한 대로 사용자는 eDiscovery 매니저 역할 그룹의 구성원이거나 검색 사서함에 대한 준수 검색 관리 역할이 할당되어야 합니다. 메시지를 삭제하려면 사용자가 조직 관리 역할 그룹의 구성원이거나 검색 및 제거 관리 역할을 할당 받아야 합니다. 이렇게 하면 조직에서 사서함을 검색할 수있는 사람과 메시지를 삭제할 수 있는 사람을 제어할 수 있습니다.
