---
title: 비활성 사서함 만들기 및 관리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
description: Office 365의 비활성 사서함 기능을 사용하여 삭제된 사서함의 콘텐츠를 보존하는 방법을 학습합니다.
ms.openlocfilehash: 45de882cf0931b85d3acd6368f619f94fce636d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908382"
---
# <a name="create-and-manage-inactive-mailboxes"></a>비활성 사서함 만들기 및 관리

Microsoft 365를 사용하면 삭제된 사서함의 내용을 보존할 수 있습니다. 이 기능을 [비활성 사서함](inactive-mailboxes-in-office-365.md)이라고 합니다. 비활성 사서함을 사용하면 조직에서 나서 이전 직원의 전자 메일을 보존할 수 있습니다. 해당 사용자 계정이 삭제되기 전에 사서함에 소송 보존 또는 보존 정책(Office 365 또는 Microsoft 365의 보안 및 준수 센터에서 생성)이 적용되면 사서함이 비활성화됩니다. 비활성 사서함의 콘텐츠는 비활성으로 설정되기 전에 사서함에 배치된 보존 기간 동안 보존됩니다. 이를 통해 관리자, 준수 관리자 및 레코드 관리자는 콘텐츠 검색을 사용하여 비활성 사서함의 콘텐츠를 검색하고 내보낼 수 있습니다. 비활성 사서함은 전자 메일을 받을 수 없으며 조직의 공유 주소록 또는 기타 목록에 표시되지 않습니다.
  
> [!IMPORTANT]
> 사서함 콘텐츠를 보존하는 다양한 방식으로 계속 투자함에 따라 Exchange 관리 센터에서 In-Place 보존의 사용 중지를 발표합니다. 즉, 소송 보존 및 보존 정책을 사용하여 비활성 사서함을 만들어야 합니다. 2020년 7월 1일부터는 Exchange Online에서 보류를 In-Place 수 없습니다. 그러나 비활성 사서함에 배치된 보류 In-Place 변경할 수 있습니다. 그러나 2020년 10월 1일부터는 보류 기간을 변경할 수 없습니다. 비활성 사서함은 비활성 사서함을 제거하여 비활성 사서함만 삭제할 In-Place 있습니다. 보류에 있는 In-Place 비활성 사서함은 보존이 제거될 때까지 계속 보존됩니다. 보류의 사용 중지에 대한 In-Place 레거시 [eDiscovery](legacy-ediscovery-retirement.md)도구의 사용 중지를 참조하세요.
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>비활성 사서함을 만들기 전에 준비

- 사서함을 비활성화하려면 사서함을 삭제하기 전에 사서함에 소송 보존 또는 보존 정책을 적용할 수 있도록 Exchange Online 계획 2 라이선스를 할당해야 합니다. Exchange Online 계획 2 라이선스는 Office 365 Enterprise E3 및 E5 구독의 일부입니다. 사서함에 Exchange Online 계획 1 또는 Exchange Online Kiosk 라이선스가 할당된 경우(각각 Office 365 E1 및 F1 구독의 일부인) 사서함을 삭제하기 전에 보류를 적용할 수 있도록 별도의 Exchange Online Archiving 라이선스를 할당해야 합니다. 자세한 내용은 [을](https://go.microsoft.com/fwlink/p/?LinkId=286153)Exchange Online Archiving.

- 해당 사용자 계정을 삭제한 후 삭제된 Exchange Online 사서함과 연결된 라이선스를 사용할 수 있습니다. 그런 다음 해당 라이선스를 다른 사용자에게 [할당할 수 있습니다.](../admin/manage/assign-licenses-to-users.md)

- 콘텐츠를 보존하거나 보존한 다음 삭제하도록 구성된 보존 정책 또는 소송 보존 정책이 삭제되기 전에 사서함에 적용되지 않는 경우 사서함의 콘텐츠는 보존되거나 검색할 수 없습니다. 그러나 삭제된 사서함은 삭제 후 30일 이내에 복구할 수 있지만 복구되지 않은 경우 30일 후에 사서함 및 해당 콘텐츠가 영구적으로 삭제됩니다.

- 소송 보유에 대한 자세한 내용은 [In-Place Hold and Litigation Hold를 참조하십시오.](/exchange/security-and-compliance/in-place-and-litigation-holds) 보존 정책에 대한 자세한 내용은 보존 정책 및 보존 레이블에 대해 [자세히를 참조하세요.](retention.md)
  
## <a name="create-an-inactive-mailbox"></a>비활성 사서함 만들기

사서함을 비활성화하려면 1) 사서함을 소송 보존으로 설정하거나 보존 정책을 적용하고, 2) 사서함 또는 해당 사용자 계정을 삭제하는 두 단계가 수행됩니다. 사서함이 비활성인 경우 보존 또는 보존 정책이 제거될 때까지 해당 콘텐츠가 보존됩니다.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>1단계: 사서함에 소송 보존 적용 또는 보존 정책 적용

사서함을 소송 보존으로 설정하거나 보존 정책(콘텐츠를 보존하거나 보존한 다음 삭제하도록 구성된 보존 정책)을 적용하면 사서함이 삭제되기 전에 사서함의 콘텐츠가 보존됩니다. 두 보존 유형 모두 삭제된 항목 및 수정된 항목의 원래 버전을 포함하여 모든 사서함 콘텐츠를 보존합니다. 삭제 및 수정된 항목은 지정된 기간 동안 비활성 사서함에 보존되거나 비활성 사서함에 적용된 보존 또는 보존 정책을 제거하여 비활성 사서함을 영구적으로 삭제할 때까지 보존됩니다.
  
이미 사서함에 보류가 적용되어 있는 경우 또는 보존 정책이 사서함에 이미 적용된 경우 2단계에서 설명한 해당 사용자 계정을 삭제하기만하면 됩니다.
  
사서함을 소송 보존으로 설정하거나 보존 정책을 적용하는 단계별 절차는 다음을 참조합니다.
  
- [사서함을 소송 자료 보존으로 설정](./create-a-litigation-hold.md)
    
- [Office 365의 보존 정책 및 보존 레이블에 대한 자세한 정보](retention.md)
    
> [!NOTE]
> 소송 보존 및 보존 정책의 경우 무기한 보류를 만들거나 시간 기반 보류를 만들 수 있습니다. 무기한 보존의 경우 비활성 사서함의 콘텐츠는 보존이 제거되거나 보존 기간이 변경될 때까지 계속 보존됩니다. 보류 또는 보존 정책이 제거된 후(사서함이 30일 이상 삭제된 경우) 비활성 사서함은 영구 삭제로 표시되고 사서함의 콘텐츠는 더 이상 보존되거나 검색할 수 없습니다. 시간 기반 보류 또는 보존 정책에서 보존 기간을 지정합니다. 이 기간은 항목별로 지정되며 사서함 항목을 받거나 만든 날짜로부터 계산됩니다. 사서함 항목에 대한 보류가 만료되고 해당 항목이 비활성 사서함의 복구 가능한 항목 폴더로 이동되거나 해당 폴더에 있는 경우 삭제된 항목 보존 기간이 만료되면 해당 항목이 비활성 사서함에서 영구적으로 삭제(제거)됩니다. 
  
### <a name="step-2-delete-the-mailbox"></a>2단계: 사서함 삭제

사서함을 보류하거나 보존 정책이 사서함에 적용된 후 다음 단계는 사서함을 삭제하는 것입니다. 사서함을 삭제하는 가장 좋은 방법은 Microsoft 365 관리 센터에서 해당 사용자 계정을 삭제하는 것입니다. 사용자 계정을 삭제하는 데 대한 자세한 내용은 조직에서 사용자 [삭제를 참조하세요.](../admin/add-users/delete-a-user.md)
  
> [!NOTE]
> Exchange Online PowerShell에서 **Remove-Mailbox** cmdlet을 사용하여 사서함을 삭제할 수도 있습니다. 자세한 내용은 Exchange Online에서 사용자 사서함 삭제 또는 [복원을 참조하세요.](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>비활성 사서함 목록 보기

조직의 비활성 사서함 목록을 확인 합니다.
  
1. [https://protection.office.com](https://protection.office.com)으로 이동한 후 조직의 관리자 계정 자격 증명을 사용하여 로그인합니다. 
    
2. 정보 **거버넌스 보존을**  >  **클릭합니다.**
    
3. 보존 **페이지에서** 추가 **탐색** 모음 타원을 클릭한 다음 비활성 사서함 ![ ](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) **을 클릭합니다.**
    
    ![보존 페이지에서 추가를 클릭한 다음 비활성 사서함을 클릭하여 비활성 사서함 목록을 표시합니다.](../media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    **비활성 사서함 페이지가** 표시됩니다. 조직의 총 비활성 사서함 수가 표시됩니다. 
    
    ![조직의 모든 비활성 사서함 목록이 표시됩니다.](../media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
또는 Exchange Online PowerShell에서 다음 명령을 실행하여 비활성 사서함 목록을 표시할 수 있습니다.

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

검색 결과 내보내기 아이콘 내보내기 를 클릭하여 조직의 비활성 사서함에 대한 추가 정보가 포함된 CSV 파일을 보거나 다운로드할 ![ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)  수 있습니다. 
  
다음 명령을 실행하여 비활성 사서함 목록 및 기타 정보를 CSV 파일로 내보낼 수도 있습니다. 이 예에서는 CSV 파일이 현재 디렉터리에 만들어집니다.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> 비활성 사서함에 활성 사용자 사서함과 동일한 SMTP 주소가 있을 수 있습니다. 이 경우 **DistinguishedName** 또는 **ExchangeGuid** 속성 값을 사용하여 비활성 사서함을 고유하게 식별할 수 있습니다. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>비활성 사서함의 콘텐츠 검색 및 내보내기

보안 및 준수 센터의 콘텐츠 검색 도구를 사용하여 비활성 사서함의 콘텐츠에 액세스할 & 있습니다. 비활성 사서함을 검색할 때는 키워드 검색 쿼리를 만들어 특정 항목을 검색하거나 비활성 사서함의 전체 콘텐츠를 반환할 수 있습니다. 검색 결과를 미리 보거나 검색 결과를 Outlook 데이터(PST) 파일 또는 개별 전자 메일 메시지로 내보낼 수 있습니다. 사서함을 검색하고 검색 결과를 내보내는 단계별 절차는 다음 항목을 참조하십시오.
  
- [Office 365의 콘텐츠 검색](content-search.md)
    
- [콘텐츠 검색 결과 내보내기](export-search-results.md)
    
다음은 비활성 사서함을 검색할 때 유의해야 하는 몇 가지 사항입니다.
  
- 콘텐츠 검색에 사용자 사서함이 포함되어 있으며 해당 사서함이 비활성으로 설정되는 경우 콘텐츠 검색은 비활성으로 된 후 검색을 다시 한 후에도 비활성 사서함을 계속 검색합니다.
    
- 경우에 따라 사용자에게 활성 사서함과 동일한 SMTP 주소가 있는 비활성 사서함이 있을 수 있습니다. 이 경우 콘텐츠 검색 위치로 선택한 특정 사서함만 검색됩니다. 즉, 사용자의 사서함을 검색에 추가하는 경우 활성 사서함과 비활성 사서함이 모두 검색된다고 가정할 수 없습니다. 검색에 명시적으로 추가한 사서함만 검색됩니다.
    
- 동일한 SMTP 주소를 사용하는 활성 사서함과 비활성 사서함은 없는 것이 좋습니다. 현재 비활성 사서함에 할당된 SMTP 주소를 다시 사용하려면 비활성 사서함을 복구하거나 비활성 사서함의 내용을 활성 사서함(또는 활성 사서함의 보관함)으로 복원한 다음 비활성 사서함을 삭제하는 것이 좋습니다.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>비활성 사서함의 보존 기간 변경

사서함을 비활성으로 설정한 후 보존 기간 또는 비활성 사서함에 적용 된 보존 정책을 변경할 수 있습니다. 단계별 절차는 [Office 365에서](change-the-hold-duration-for-an-inactive-mailbox.md)비활성 사서함의 보류 기간 변경을 참조합니다.
  
## <a name="recover-an-inactive-mailbox"></a>비활성 사서함 복구

이전 직원이 조직으로 돌아오거나 퇴사한 직원의 직무를 위해 신입 사원을 고용한 경우 비활성 사서함의 내용을 복구할 수 있습니다. 비활성 사서함을 복구 하는 경우 사서함 새 사서함으로 변환 됩니다 내용과 비활성 사서함의 폴더 구조 유지 되므로 및 사서함을 새 사용자 계정에 연결 됩니다. 복구한 후 비활성 사서함 존재 하지 않습니다. 비활성 사서함을 복구할 때 발생하는 단계별 절차 및 자세한 내용은 [Office 365에서](recover-an-inactive-mailbox.md)비활성 사서함 복구를 참조하세요.
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>비활성 사서함의 콘텐츠를 다른 사서함으로 복원

다른 직원이 이전 직원의 직무를 대신하거나 다른 사람이 비활성 사서함의 콘텐츠에 액세스해야 하는 경우 비활성 사서함의 내용을 기존 사서함으로 복원하거나 병합할 수 있습니다. 비활성 사서함을 복원 하는 경우에 내용은 다른 사서함에 복사 됩니다. 비활성 사서함은 유지 하 고 비활성 사서함을 유지 됩니다. eDiscovery를 사용하여 비활성 사서함을 계속 검색하거나 해당 콘텐츠를 다른 사서함으로 복원하거나 나중에 복구하거나 삭제할 수 있습니다. 단계별 절차는 [Office 365에서](restore-an-inactive-mailbox.md)비활성 사서함 복원을 참조합니다.
  
## <a name="delete-an-inactive-mailbox"></a>비활성 사서함 삭제

비활성 사서함의 콘텐츠를 더 이상 보존할 필요가 없는 경우 비활성 사서함에 적용된 보존 정책을 제거하거나 보존을 제거하여 비활성 사서함을 영구적으로 삭제할 수 있습니다. 사서함이 30일 이상 삭제된 경우 보류를 제거하면 사서함이 영구적으로 삭제된 것으로 표시되고 사서함을 복구할 수 없습니다. 지난 30일 이내에 사서함이 삭제된 경우 보류 또는 보존 정책을 제거한 후에도 사서함을 복구할 수 있습니다. 비활성 사서함을 영구적으로 삭제하기 위한 보존 또는 보존 정책을 제거하는 단계별 절차는 비활성 사서함 [삭제를 참조합니다.](delete-an-inactive-mailbox.md)