---
title: Microsoft 365 규정 준수 센터의 보관 사서함 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: 준수 센터를 사용하여 조직의 메시지 보존, eDiscovery 및 보유 요구 사항을 지원하기 위해 보관 사서함을 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 0519853f526254173c086ff353c6e5f5cf0208a2
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786377"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a>준수 센터에서 보관 사서함 사용

Microsoft 365(*내부 보관* 이라고도 함)의 보관은 사용자에게 추가 사서함 저장소 공간을 제공합니다. 보관 사서함을 설정하면 사용자가 웹의 Microsoft Outlook 및 Outlook(이전의 Outlook Web App)을 사용하여 보관 사서함에 메시지를 액세스하고 저장할 수 있습니다. 또한 사용자는 기본 사서함과 보관 사서함 간에 메시지를 이동하거나 복사할 수 있습니다. 또한 지운 편지함 복구 도구를 사용하여 보관 사서함의 복구 가능한 항목 폴더에서 삭제된 항목을 복구할 수 있습니다.

> [!NOTE]
> Microsoft 365의 자동 확장 보관 기능은 보관 사서함에 추가 저장소를 제공합니다. 자동 확장 보관 기능이 켜져 있고 사용자 보관 사서함의 초기 저장소 할당량에 도달하면 Microsoft 365가 자동으로 추가 저장 공간을 추가합니다. 즉, 사용자가 사서함 저장 공간을 모두 소모하지 않으므로 처음에 보관 사서함을 사용하도록 설정하고 조직의 자동 확장 보관을 설정한 후에는 아무 것도 관리할 필요가 없습니다. 자세한 내용은 [자동 확장 보관 개요](autoexpanding-archiving.md)를 참조하세요.

## <a name="get-the-necessary-permissions"></a>필요한 사용 권한 얻기

보관 사서함을 사용하거나 사용하지 않도록 설정하려면 Exchange Online에서 메일받는 사람 역할을 할당받아야합니다. 기본적으로 이 역할은 Exchange 관리 센터의 **사용 권한** 페이지에서 받는 사람 관리 및 조직 관리 역할 그룹에 할당됩니다. Microsoft 365 규정 준수 센터에서 **보관함** 페이지가 보이지 않으면 관리자에게 필요한 권한을 할당해 줄 것을 요청하십시오.

## <a name="enable-an-archive-mailbox"></a>보관 사서함 사용

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>로 이동하여 로그인합니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 창에서 **정보 거버넌스** 를 클릭하고 **보관** 탭을 클릭합니다.

   **보관** 페이지가 표시됩니다. **보관 사서함** 열은 각 사용자의 보관 사서함이 사용하도록 설정되었는지 여부를 나타냅니다.

   > [!NOTE]
   > **보관** 페이지에는 최대 500명의 사용자가 표시됩니다.

4. 사서함 목록에서 보관 사서함을 사용하도록 설정할 사용자를 선택합니다.

   ![선택한 사용자의 세부 정보 창에서 사용을 클릭하여 보관 사서함을 사용하도록 설정합니다.](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

5. 선택한 사용자의 세부 정보 창에서 **사용** 을 클릭합니다.

   보관 사서함이 사용되도록 설정된다는 경고가 표시되고, 사서함에 할당된 보존 정책보다 오래된 사용자의 사서함 항목이 새 보관 사서함으로 이동됩니다. ExchangeOnline 사서함에 할당된 보존 정책에 속하는 기본 보관 정책은 사용자가 항목을 사서함으로 전달하거나 만든 날짜로부터 2년 후에 항목을 보관 사서함으로 이동합니다. 자세한 내용은 이 문서의 **추가 정보** 섹션을 참조하십시오.

6. **예** 를 클릭하여 보관 사서함을 사용하도록 설정합니다.

   보관 사서함을 만드는 몇 분 정도 걸릴 수 있습니다. 생성되면 **보관 사서함: 사용 가능** 이 선택한 사용자의 세부 정보 창에 표시됩니다. **새로 고침** ![새로 고침 아이콘](../media/O365-MDM-Policy-RefreshIcon.gif)을 클릭해야 할 수도 있습니다. 세부 정보 창의 정보를 업데이트하려면

> [!TIP]
> Shift 또는 Ctrl 키를 사용해 여러 사서함을 선택하여 보관함을 대량으로 사용하도록 설정할 수도 있습니다. 여러 사서함을 선택한 후 세부 정보 창에서 기타 옵션을 클릭합니다. 그런 후에 보관함에서 **사용** 을 클릭합니다.

## <a name="disable-an-archive-mailbox"></a>보관 사서함 사용 안 함

Microsoft 365 규정 준수 센터의 **보관** 페이지에서 사용자의 보관 사서함을 사용하지 않도록 설정할 수도 있습니다. 보관 사서함을 비활성화 한 후 다시 연결할 수 있습니다이 사용자의 기본 사서함을 해제 후 30 일 이내. 이 경우 보관 사서함의 원래 내용은 복원 됩니다. 30 일이 지나면 원래 보관 사서함의 내용을 영구적으로 삭제 하 고 복구할 수 없습니다. 따라서 아카이브 해제 한 후 30 일 이상 다시 설정, 보관 사서함이 새로 만들어집니다.

사용자의 사서함에 할당된 기본 보관 정책은 항목이 전달된 날짜로부터 2년 후에 항목을 보관 사서함으로 이동합니다. 사용자의 보관 사서함을 사용하지 않도록 설정하면 사서함 항목에 대해 아무 작업도 수행되지 않으며 사용자의 기본 사서함에 그대로 남아 있습니다.

보관 사서함을 사용하지 않으려면:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>로 이동하여 로그인합니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 창에서 **정보 거버넌스** 를 클릭하고 **보관** 탭을 클릭합니다.

   **보관** 페이지가 표시됩니다. **보관 사서함** 열은 각 사용자의 보관 사서함이 사용하도록 설정되었는지 여부를 나타냅니다.

   > [!NOTE]
   > **보관** 페이지에는 최대 500명의 사용자가 표시됩니다.

3. 사서함 목록에서 보관 사서함을 사용하지 않도록 설정할 사용자를 선택합니다.

4. 세부 정보 창에서 **사용 안 함** 을 클릭합니다.

   30일 이내에 보관 사서함을 다시 사용하도록 설정해야 하고, 30일 이후에는 보관 사서함의 모든 정보가 영구적으로 삭제된다는 경고 메시지가 표시됩니다.

5. **예** 를 클릭하여 보관 사서함을 사용하지 않도록 설정합니다.

   보관 사서함을 사용 해제하는 데 몇 분 정도 걸릴 수 있습니다. 사용하지 않도록 설정하면 **보관 사서함: 사용하지 않음** 이 선택한 사용자의 세부 정보 창에 표시됩니다. **새로 고침** ![새로 고침 아이콘](../media/O365-MDM-Policy-RefreshIcon.gif)을 클릭해야 할 수도 있습니다. 세부 정보 창의 정보를 업데이트하려면

> [!TIP]
> Shift 또는 Ctrl 키를 사용해 보관 사서함이 사용하도록 설정된 여러 사용자를 선택하여 보관 사서함을 사용하지 않도록 일괄 설정할 수도 있습니다. 여러 사서함을 선택한 후 세부 정보 창에서 **사용 안 함** 을 클릭합니다.

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Exchange Online PowerShell을 사용하여 보관 사서함을 사용하거나 사용하지 않도록 설정

Exchange Online PowerShell을 사용하여 보관 사서함을 사용할 수도 있습니다. PowerShell을 사용하는 주된 이유는 조직의 모든 사용자에 대해 보관 사서함을 신속하게 사용할 수 있다는 것입니다.

첫 번째 단계는 Exchange Online PowerShell에 연결하는 것입니다. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

Exchange Online에 연결되면 다음 섹션의 명령을 실행하여 보관 사서함을 사용하거나 사용하지 않도록 설정할 수 있습니다.

### <a name="enable-archive-mailboxes"></a>보관 사서함 사용

다음 명령을 실행하여 단일 사용자가 보관 사서함을 사용하도록 설정합니다.

```powershell
Enable-Mailbox -Identity <username> -Archive
```

다음 명령을 실행하여 조직의 모든 사용자(현재 보관 사서함을 사용할 수 없는 사용자)의 보관 사서함을 사용하도록 설정합니다.

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a>보관 사서함을 사용하지 않도록 설정

다음 명령을 실행하여 단일 사용자가 보관 사서함을 사용하지 않도록 설정합니다.

```powershell
Disable-Mailbox -Identity <username> -Archive
```

다음 명령을 실행하여 조직의 모든 사용자(현재 보관 사서함을 사용할 수 있는 사용자)의 보관 사서함을 사용하지 않도록 설정합니다.

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="more-information"></a>추가 정보

- 보관 사서함을 사용하도록 설정하면 사용자는 보관 사서함에 메시지를 저장할 수 있습니다. 사용자는 웹에서 Microsoft Outlook 및 Outlook을 사용하여 보관 사서함에 액세스할 수 있습니다. 이러한 클라이언트 응용 프로그램을 사용하여 사용자는 보관 사서함의 메시지를 보고 기본 사서함과 보관 사서함 간에 메시지를 이동하거나 복사할 수 있습니다. 사용자는 지운 편지함 복구 도구를 사용하여 보관 사서함의 복구 가능한 항목 폴더에서 삭제된 항목을 복구할 수 있습니다.

  현재 위치 보관을 지원하는 Outlook 라이선스 목록은 [Exchange 기능](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99)의 Outlook 라이선스 요구 사항을 참조하십시오.

- 보관 사서함은 사용자가 조직의 보존, eDiscovery 및 보류 요구 사항을 충족하는 데 도움이 됩니다. 예를 들어, 조직의 Exchange 보존 정책을 사용하여 사용자의 보관 사서함으로 사서함 콘텐츠를 이동할 수 있습니다. Microsoft 365 규정 준수 센터의 콘텐츠 검색 도구를 사용하여 사용자 사서함의 특정 콘텐츠를 검색하면 해당 사용자의 보관 사서함도 검색됩니다. 또한 소송 보존을 배치하거나 보존 정책을 사용자의 사서함에 적용하면 보관 사서함의 항목도 보존됩니다.

- 보관 사서함을 사용하도록 설정하면 조직에서 모든 사서함에 자동으로 할당되는 기본 Exchange 보존 정책(메시징 레코드 관리 또는 MRM 정책이라고도 함)을 활용할 수 있습니다. 보관 사서함을 사용하도록 설정하면 기본 Exchange 보존 정책이 자동으로 다음 작업을 수행합니다.

  - 사용자의 기본 사서함에서 보관 사서함으로 2년 이상 된 항목을 이동합니다.

  - 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더에서 보관 사서함의 복구 가능한 항목 폴더로 14일 이상 된 항목을 이동합니다.

- 보관 사서함 및 Exchange 보존 정책에 대한 자세한 내용은 다음을 참조하십시오.

  - [Exchange Online의 보존 태그 및 보존 정책](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

  - [Exchange Online의 기본 보존 정책](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

  - [조직에서 사서함에 대한 보관 및 삭제 정책 설정하기](set-up-an-archive-and-deletion-policy-for-mailboxes.md)