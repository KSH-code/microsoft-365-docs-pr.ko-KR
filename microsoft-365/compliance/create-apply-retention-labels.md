---
title: 콘텐츠를 보존하거나 삭제하는 보존 레이블을 만들고 앱에 적용하기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 레이블을 만들어서 게시한 후에 필요한 항목은 보존하고 필요하지 않은 항목은 삭제하도록 앱에 적용하기 위한 지침입니다.
ms.openlocfilehash: f86692d07f7636f35ba700b9750510219a6ef380
ms.sourcegitcommit: f6fff04431d632db02e7bdbf12f691091a30efad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60432640"
---
# <a name="create-retention-labels-and-apply-them-in-apps"></a>보존 레이블을 만들고 앱에 적용

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> 이 시나리오는 [규제 기록](records-management.md#records)을 포함하여 모든 보존 레이블 구성에 대해 지원됩니다.

다음 정보를 사용하여 [보존 레이블](retention.md)을 만들어서 게시한 다음 문서 및 전자 메일에 적용하는 데 도움을 받습니다.

보존 레이블은 항목 수준(문서 또는 전자 메일)에서 필요한 항목은 보존하고 필요하지 않은 항목은 삭제할 수 있게 해줍니다. 또한 Microsoft 365 데이터에 대한 [레코드 관리](records-management.md) 솔루션의 일부로 항목을 레코드로 선언하는 데에도 사용됩니다.

콘텐츠를 분류할 수 있도록 조직의 사용자에게 보존 레이블을 제공하는 작업은 2단계 프로세스입니다. 

1. 보존 레이블을 만듭니다.

2. 보존 레이블 정책을 사용하여 보존 레이블을 게시합니다.
  
![레이블의 역할 및 작업 다이어그램.](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)

두 가지 관리 단계를 수행하려면 다음 지침을 사용합니다.

## <a name="before-you-begin"></a>시작하기 전에

조직의 전역 관리자는 보존 레이블과 해당 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다. 전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.

보존 레이블 정책을 만들기 전에 **적응형** 또는 **정적** 정책인지 결정합니다. 자세한 내용은 [보존을 위한 적응형 또는 정적 정책 범위](retention.md#adaptive-or-static-policy-scopes-for-retention)를 참조하세요. 적응형 정책을 사용하기로 결정한 경우 보존 레이블 정책을 만들기 전에 하나 이상의 적응형 범위를 만든 다음 보존 레이블 정책 만들기 프로세스 중에 선택해야 합니다. 자세한 내용은 [적응형 범위에 대한 구성 정보](retention-settings.md#configuration-information-for-adaptive-scopes)를 참조하세요.

## <a name="how-to-create-and-publish-retention-labels"></a>보존 레이블을 만들고 게시하는 방법

먼저 보존 레이블을 만듭니다. 그런 다음 레이블을 앱에 적용할 수 있게 되는 레이블 정책을 만듭니다.

보존 레이블을 만들고 구성하는 위치는 레코드 관리를 사용 중인지 여부에 따라 달라집니다. 두 시나리오 모두에 대한 지침이 제공 됩니다.

### <a name="step-1-create-retention-labels"></a>1단계: 보존 레이블 만들기

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.
    
    - 레코드 관리를 사용하는 경우:
        - **솔루션** > **레코드 관리** > **파일 계획** 탭 > **+ 레이블 만들기** > **보존 레이블**
        
    - 레코드 관리를 사용하지 않는 경우:
       - **솔루션** > **정보 관리** > **레이블** tab > + **레이블 만들기**
    
    탐색 창에 솔루션이 즉시 표시되지 않나요? 먼저 **모두 표시** 를 선택합니다. 

2. 마법사의 지시를 따릅니다.
    
    보존 설정에 대한 자세한 내용은 [콘텐츠 보존 및 삭제 설정](retention-settings.md#settings-for-retaining-and-deleting-content)을 참조하세요.
    
    레코드 관리를 사용하는 경우:
    
    - 파일 계획 설명자에 대한 자세한 내용은 [파일 계획을 사용하여 보존 레이블 관리의 개요](file-plan-manager.md)를 참조하세요.
    
    - 보존 레이블을 사용하여 레코드를 선언하려면 **항목을 레코드로 표시** 를 선택하거나 **항목을 규제 레코드로 표시** 를 선택합니다. 자세한 정보는 [레코드를 선언하도록 보존 레이블 구성하기](declare-records.md#configuring-retention-labels-to-declare-records)를 참조하세요.

3. 레이블을 만든 후에는 레이블을 게시하는 옵션이 표시되고, 레이블을 자동으로 적용하거나, 단지 레이블을 저장합니다. **지금 레이블을 저장** 하고, 그 후 **완료** 를 선택합니다.

4. 이 단계를 반복하여 레이블을 더 만듭니다.

기존 레이블을 편집하려면 레이블을 선택한 후 **레이블 편집** 옵션을 선택하여 레이블 설명과 [적격 설정](#updating-retention-labels-and-their-policies)을 변경하는 데 사용하는 편집 보유 마법사를 2단계에서 시작합니다.

### <a name="step-2-publish-retention-labels"></a>2단계: 보존 레이블 게시

SharePoint 및 Outlook과 같은 앱에서 사용자가 적용할 수 있도록 보존 레이블을 게시합니다.

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.
    
    - 레코드 관리를 사용하는 경우:
        - **솔루션** > **레코드 관리** > > **레이블 정책** 탭 > **레이블 게시**
    
    - 레코드 관리를 사용하지 않는 경우:
        - **솔루션** > **정보 관리** > **레이블 정책** 탭 > **레이블 게시**
    
    탐색 창에 솔루션이 즉시 표시되지 않나요? 먼저 **모두 표시** 를 선택합니다. 

2. 링크를 사용하여 게시할 보존 라벨을 선택한 후 **다음** 을 선택합니다.

3. **생성할 보존 정책 유형 선택** 페이지에서 [시작하기 전](#before-you-begin) 지침에서 선택한 항목에 따라 **적응형** 또는 **정적** 을 선택합니다. 적응형 범위를 아직 만들지 않은 경우 **적응형** 을 선택할 수 있지만 선택할 적응형 범위가 없기 때문에 이 옵션으로 마법사를 완료할 수 없습니다.

4. 선택한 범위에 따라:
    
    - **적응형** 을 선택한 경우: **적응형 정책 범위 및 위치 선택** 페이지에서 **범위 추가** 를 선택하고 생성된 하나 이상의 적응형 범위를 선택합니다. 그런 다음 하나 이상의 위치를 ​​선택합니다. 선택할 수 있는 위치는 추가된 [범위 유형](retention-settings.md#configuration-information-for-adaptive-scopes)에 따라 다릅니다. 예를 들어 **사용자** 의 범위 유형만 추가한 경우 **Exchange 이메일** 은 선택할 수 있지만 **SharePoint 사이트** 는 선택할 수 없습니다. 
    
    - **정적** 을 선택한 경우: **위치 선택** 페이지에서 위치를 켜거나 끕니다. 각 위치에 대해 기본값으로 두어 [전체 위치에 정책을 적용](retention-settings.md#a-policy-that-applies-to-entire-locations)하거나 [포함 및 제외를 지정](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions)할 수 있습니다.
    
    위치 선택에 대한 자세한 내용은 [위치](retention-settings.md#locations)를 참조하세요.

5.  마법사의 프롬프트에 따라 정책 이름을 지정하고 구성 선택 사항을 검토한 후 제출합니다.
    
    위치 선택에 대한 자세한 내용은 [위치](retention-settings.md#locations)를 참조하세요. 

기존 보존 레이블 정책(정책 유형은 **게시**)을 편집 하려면, 이를 선택하고 그 후 **편집** 옵션을 선택하여 보존 정책 편집을 시작합니다. 이 마법사를 사용하면 정책 설명과 모든 [적격 설정](#updating-retention-labels-and-their-policies)을 변경할 수 있습니다.

## <a name="when-retention-labels-become-available-to-apply"></a>보존 레이블을 적용할 수 있게 되면

SharePoint 또는 OneDrive에 보존 레이블을 게시하면 일반적으로 1일 이내에 최종 사용자가 선택하도록 레이블이 표시됩니다. 그러나 최대 7일까지 걸릴 수 있습니다. 

보존 레이블을 Exchange에 게시하는 경우 해당 보존 레이블이 최종 사용자에게 표시되기까지 최대 7일이 걸릴 수 있으며 사서함에 10MB 이상의 데이터를 저장할 수 있어야 합니다.

예제:
  
![수동 레이블이 적용되는 경우를 나타내는 다이어그램.](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  

7일 후에 레이블이 표시되지 않는 경우, 준수 센터의 **레이블 정책** 페이지에서 레이블 정책을 선택하여 그 **상태** 를 확인합니다. **꺼짐(오류)** 의 상태가 표시되고 위치에 대한 세부 정보에 정책을 배포하거나(SharePoint의 경우) 혹은 정책 재배포를 시도하는 데(OneDrive의 경우) 예상보다 시간이 오래 걸리고 있다는 메시지가 표시되는 경우, [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell 명령을 실행하여 정책 배포를 다시 시도하세요.

1. [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)

2. 다음 명령을 실행합니다.
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>Exchange에 게시된 보존 레이블의 상태를 확인하는 방법

Exchange Online에서는 7일 간격으로 실행되는 프로세스를 통해 최종 사용자가 보존 레이블을 사용할 수 있게 됩니다. Powershell을 사용하여 이 프로세스가 마지막으로 실행된 시간 및 다시 실행될 시간을 파악할 수 있습니다.
  
1. [Exchange Online PowerShell에 연결합니다](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. 다음 명령을 실행합니다.
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## How to apply published retention labels

Use the following sections to learn how published retention labels can be applied in apps:

- [Manually apply retention labels](#manually-apply-retention-labels)

- [Applying a default retention label to all content in a SharePoint library, folder, or document set](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)

- [Automatically applying a retention label to email by using rules](#automatically-applying-a-retention-label-to-email-by-using-rules)

In addition, when you use [SharePoint Syntex](../contentunderstanding/index.md) and publish retention labels to SharePoint locations, you can [apply a retention label to a document understanding model](../contentunderstanding/apply-a-retention-label-to-a-model.md) so that identified documents are automatically labeled.

After content is labeled, see the following information to understand when the applied label can be removed or changed: [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).

### Manually apply retention labels 

End users, as well as administrators, can manually apply retention labels from the following locations:  

- Outlook and Outlook on the web
    
- OneDrive
    
- SharePoint
    
- Microsoft 365 groups (both the group site and group mailbox in Outlook on the web)
    
Use the following sections to understand how to apply retention labels. 

#### Applying retention labels in Outlook

To label an item in the Outlook desktop client, select the item. On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label. 
  
![Assign Policy button.](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label. When you select multiple items, you can use this method to assign the same retention label to multiple items at once.

After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.

##### Applying a default retention label to an Outlook folder

You can apply retention labels to Outlook folders as a default label that can be inherited by messages in that folder. Right-click the folder, select **Properties**, the **Policy** tab, and select the retention label you want to use as that folder's default retention label.

When you use a a standard retention label as your default label for an Outlook folder:
  
- All unlabeled items in the folder have this retention label applied.

- The inheritance flows to any child folders and items inherit the label from their nearest folder.

- Items that are already labeled retain their retention label, unless it was applied by a different default label.

- If you change or remove the default retention label for the folder: Existing retention labels applied to items in that folder are also changed or removed only if those labels were applied by a default label.

- If you move an item with a default retention label from one folder to another folder with a different default retention label: The item gets the new default retention label.

- If you move an item with a default retention label from one folder to another folder with no default retention label: The old default retention label is removed.

When labels are applied that aren't standard retention labels but mark items as [records (or regulatory records)](records-management.md#records), these labels can only be manually changed or removed.

#### Applying retention labels in Outlook on the web

To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label. Unlike Outlook desktop, you can't use this method if you multi-select items.
  
![Assign policy menu in Outlook on the web.](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![Label assigned to email in Outlook on the web.](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
As with the desktop version of Outlook on the web, you can also apply retention labels to folders. Right-click the folder, select **Assign policy**, and change **Use parent folder policy** to the retention label you want to use as that folder's default retention label.

#### Applying retention labels in OneDrive and SharePoint

To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon.](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label. 
  
You can also apply a retention label to a folder or document set, and you can set a [default retention label for a document library](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Apply label list for an item in SharePoint.](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
After a retention label is applied to an item, you can view it in the details pane when that item's selected.
  
![Applied label shown in Details pane.](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)

For SharePoint, but not OneDrive, you can create a view of the library that contains the **Labels** column or **Item is a Record** column. This view lets you see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column. For instructions how to add columns, see [Show or hide columns in a list or library](https://support.microsoft.com/en-us/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).


#### Applying retention labels in Microsoft 365 groups

When you publish retention labels to Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that for email and documents.

To retain content for a Microsoft 365 group, use the **Microsoft 365 Groups** location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.

In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.

### Applying a default retention label to all content in a SharePoint library, folder, or document set

This method requires retention labels to be published to a retention label policy.

In addition to letting people apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set. In this scenario, documents in that location can inherit your selected default retention label. Although the same label is applied, each document will be retained and deleted separately, according to the start of the retention period setting in the label. 
  
For a document library, the default label configuration is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to existing items in the library.
  
For example, if you have a retention label for marketing materials, and you know a specific document library contains only that type of content, you can make the **Marketing Materials** retention label the default label for all documents in that library.
  
![Apply label option on library Settings page.](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)

#### Label behavior when you use a default label for SharePoint

For standard retention labels that you apply as a default retention label to a library, folder, or document set:

- All new, unlabeled items in the container will have this retention label applied.

- For folders, the inheritance flows to any child folders and items inherit the label from their nearest folder.

- If you selected the option to apply the default label to existing items: Items that are already labeled retain their retention label, unless it was applied by a different default label.
    
- If you change the default retention label for the container: Existing retention labels applied to items in that container are changed only if you selected the option to apply the default label to existing items and those labels were applied by a default label.

- If you remove the default retention label for the container: Items retain their labels.
    
- If you move an item with a default retention label applied from one container to another container: The item keeps its existing default retention label, even if the new location has a different default retention label. Only if you then change the default label for this new location can the moved item inherit the default label from its current location.

When labels are applied that aren't standard retention labels but mark items as [records (or regulatory records)](records-management.md#records), these labels can only be manually changed or removed.

### Automatically applying a retention label to email by using rules

In Outlook, you can create rules to apply a retention label.
  
For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.
  
To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.
  
![Rules wizard with option to apply retention policies.](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)

Although the UI refers to retention policies, it's your retention labels that display here and can be selected, not your retention policies.

## Updating retention labels and their policies

When you edit a retention label or retention label policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention label and policy name, and the retention settings except the retention period. However, you can't change the retention period when the retention period is based on when items were labeled.
- The option to mark items as a record.

### Deleting retention labels

You can delete retention labels that aren't currently included in any retention label policies, that aren't configured for event-based retention, or mark items as regulatory records.

For retention labels that you can delete, if they have been applied to items, the deletion fails and you see a link to content explorer to identify the labeled items.

However, it can take up to two days for content explorer to show the items that are labeled. In this scenario, the retention label might be deleted without showing you the link to content explorer.

## Locking the policy to prevent changes

If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).

## Next steps

Event-based retention is another supported scenario for retention labels. For more information, see the following articles:

- [Start retention when an event occurs](event-driven-retention.md)
- [Automate event-based retention](./event-driven-retention.md#automate-events-by-using-a-rest-api)
- [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md)