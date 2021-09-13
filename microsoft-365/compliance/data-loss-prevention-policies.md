---
title: 데이터 손실 방지 참조
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: ''
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
feedback_system: None
description: 데이터 손실 방지 참조 자료
ms.openlocfilehash: 1eba9c425e66c61e63133d39a844010a499b3eb4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216872"
---
# <a name="data-loss-prevention-reference"></a>데이터 손실 방지 참조

> [!IMPORTANT]
> 이 참조 항목은 더 이상 DLP(데이터 손실 방지) 정보의 기본 Microsoft 365 않습니다. DLP 콘텐츠 집합이 업데이트 및 재구성 중입니다. 이 문서에서 다루는 항목은 업데이트된 새로운 문서로 이동될 것입니다. DLP에 대한 자세한 내용은 데이터 손실 [방지에 대한 자세한 정보를 참조하세요.](dlp-learn-about-dlp.md)

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> 데이터 손실 방지 기능은 최근 Office 365 Advanced Compliance 라이선스 사용자에 대한 Microsoft Teams 채팅 및 채널 메시지에 추가되었으며, 이는 독립 실행형 옵션으로 제공되며 Office 365 E5 및 Microsoft 365 E5 규정 준수에 포함되어 있습니다. 라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.

With a DLP policy, you can:

- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**

    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.

- **Prevent the accidental sharing of sensitive information**.

    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.

- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**

    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.

- **Help users learn how to stay compliant without interrupting their workflow.**

    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.

- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**

    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->
## <a name="create-and-manage-dlp-policies"></a>DLP 정책 만들기 및 관리

Microsoft 365 준수 센터의 데이터 손실 방지 페이지에서 DLP 정책을 생성하고 관리할 수 있습니다.

![보안 및 준수 센터의 데이터 Office 365 &amp; 페이지입니다.](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)

<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:

- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages.

- When and how to protect the content by enforcing **rules** comprised of:

  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization.

  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification.

You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.

For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA). This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions). These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.

![Diagram shows that DLP policy contains locations and rules.](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png) -->

<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

<!-- moved to dlp-policy-reference.md
If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group. Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation. You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups. A DLP policy can contain no more than 50 such inclusions and exclusions.

If you choose to include or exclude specific SharePoint sites, a DLP policy can contain no more than 100 such inclusions and exclusions. Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.

If you choose to include or exclude specific OneDrive accounts or groups, a DLP policy can contain no more than 100 user accounts or 50 groups as inclusion or exclusion.

### Rules

> [!NOTE]
> The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger. This applies only to default information types. For custom information types, the system will alert even if there is no action defined in the policy.

Rules are what enforce your business requirements on your organization's content. A policy contains one or more rules, and each rule consists of conditions and actions. For each rule, when the conditions are met, the actions are taken automatically. Rules are executed sequentially, starting with the highest-priority rule in each policy.

A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.

Here are the components of a rule, each explained below.

![Sections of the DLP rule editor.](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)

#### Conditions

Conditions are important because they determine what types of information you're looking for, and when to take an action. For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.

Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with. You can use conditions to assign different actions to different risk levels. For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.

![List showing available DLP conditions.](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)

The conditions now available can determine if:

- Content contains a type of sensitive information.

- Content contains a label. For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).

- Content is shared with people outside or inside your organization.

  > [!NOTE]
  > Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.

#### Types of sensitive information

A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**. Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.

![List of available sensitive information types.](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)

When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number. Each sensitive information type is defined and detected by using a combination of:

- Keywords.

- Internal functions to validate checksums or composition.

- Evaluation of regular expressions to find pattern matches.

- Other content examination.

This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.

#### Actions

When content matches a condition in a rule, you can apply actions to automatically protect the content.

![List of available DLP actions.](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)

With the actions now available, you can:

- **Restrict access to the content** Depending on your need, you can restrict access to content in three ways:

  1. Restrict access to content for everyone.
  2. Restrict access to content for people outside the organization.
  3. Restrict access to "Anyone with the link."

  For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document. These people can remove the sensitive information from the document or take other remedial action. When the document is in compliance, the original permissions are automatically restored. When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.

  ![Policy tip showing access to document is blocked.](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)

  For email content, this action blocks the message from being sent. Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.

  ![Warning that unauthorized recipients must be removed from the message.](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)

#### User notifications and user overrides

You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.

![User notifications and user overrides sections of DLP rule editor.](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)

The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner. In addition, you can add or remove whomever you choose from the email notification.

In addition to sending an email notification, a user notification displays a policy tip:

- In Outlook and Outlook on the web.

- For the document on a SharePoint Online or OneDrive for Business site.

- In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.

The email notification and policy tip explain why content conflicts with a DLP policy. If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification. This can help you educate users about your DLP policies and enforce them without preventing people from doing their work. Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.

Here's what a policy tip looks like in a OneDrive for Business account.

![Policy tip for a document in a OneDrive account.](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).

#### Alerts and Incident reports

When a rule is matched, you can send an alert email to your compliance officer (or any person(s) you choose) with details of the alert. This alert email will carry a link of the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) which the compliance officer can go to view the details of alert and events. The dashboard contains details of the event that triggered the alert along with details of the DLP policy matched and the sensitive content detected.

In addition, you can also send an incident report with details of the event. This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content. For email messages, the report also includes as an attachment the original message that matches a DLP policy.

> [!div class="mx-imgBorder"]
> ![Page for configuring incident reports.](../media/Alerts-and-incident-report.png)

DLP scans email differently from items in SharePoint Online or OneDrive for Business. In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an alert and incident report whenever a match is found. In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match. DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.

## Grouping and logical operators

Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number. However, in other scenarios, your DLP policy might need to identify more loosely defined data.

For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:

- Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.

    AND

- Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided. Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).

You can easily identify such loosely defined data by using grouping and logical operators (AND, OR). When you create a DLP policy, you can:

- Group sensitive information types.

- Choose the logical operator between the sensitive information types within a group and between the groups themselves.

### Choosing the operator within a group

Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.

![Group showing the operators within the group.](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)

### Adding a group

You can quickly add a group, which can have its own conditions and operator within that group.

![Add group button.](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)

### Choosing the operator between groups

Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.

For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:

- from the group **PII Identifiers** (at least one SSN number **OR** DEA number)

    **AND**

- from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)

![Groups showing the operator between groups.](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)

## The priority by which rules are processed

When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.

> [!div class="mx-imgBorder"]
> ![Rules in priority order.](../media/dlp-rules-in-priority-order.png)

After you have set up more than one DLP policy, you can change the priority of one or more policies. To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.

> [!div class="mx-imgBorder"]
> ![Set priority for a policy.](../media/dlp-set-policy-priority.png)

When content is evaluated against rules, the rules are processed in priority order. If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced. For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:

- Rule 1: only notifies users

- Rule 2: notifies users, restricts access, and allows user overrides

- Rule 3: notifies users, restricts access, and does not allow user overrides

- Rule 4: only notifies users

- Rule 5: restricts access

- Rule 6: notifies users, restricts access, and does not allow user overrides

In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.

Regarding policy tips, note that:

- Only the policy tip from the highest priority, most restrictive rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.

- If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.

-->

## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>더 쉽게 또는 더 어렵게 일치하도록 규칙 조정

DLP 정책을 만들고 설정한 후에 다음과 같은 문제가 발생하기도 합니다:

- 중요한 정보가 **아닌** 콘텐츠가 규칙과 너무 많이 일치합니다. 즉, 가양성이 너무 많습니다.

- 중요한 정보가 **있는** 콘텐츠 중 규칙과 일치하는 콘텐츠가 너무 적습니다. 즉, 중요한 정보에 대한 보호 조치가 적용되고 있지 않습니다.

이러한 문제를 해결하려면 콘텐츠가 규칙과 더 어렵게 또는 더 쉽게 일치하도록 인스턴스 수와 일치 정확도를 조정하여 규칙을 조정할 수 있습니다. 규칙에 사용되는 각 중요한 정보 유형에는 인스턴스 수와 일치 정확도가 둘 다 포함됩니다.

### <a name="instance-count"></a>인스턴스 수

인스턴스 수는 콘텐츠가 규칙과 일치하기 위해 있어야 하는 특정 중요한 정보 유형의 발생 횟수를 의미합니다. 예를 들어, 다음의 경우에 아래와 같이 콘텐츠가 규칙에 일치합니다. 콘텐츠가 1에서 9사이의 고유한 미국 또는 영국의 여권 번호를 식별하는 경우.

> [!NOTE]
> 인스턴스 수에는 중요한 정보 유형 및 키워드에 대해 **고유한** 일치 항목만 포함됩니다. 예를 들어 전자 메일에 동일한 신용 카드 번호가 10번 포함되는 경우 해당 10번은 신용 카드 번호의 단일 인스턴스로 계산됩니다.

인스턴스 수를 사용하여 규칙을 조정하려는 경우 지침은 다음과 같이 간단합니다:

- 규칙이 더 쉽게 일치하도록 하려면 **최소** 개수를 줄이고(줄이거나) **최대** 개수를 늘립니다. 숫자 값을 삭제하여 **최대** 를 **모두** 로 설정할 수도 있습니다.

- 규칙이 더 어렵게 일치하도록 하려면 **최소** 개수를 늘립니다.

일반적으로 인스턴스 수가 낮은(예: 1-9) 규칙에서는 덜 제한적인 작업(예: 사용자 알림 보내기)을 사용합니다. 또한 인스턴스 수가 높은(예: 10-모두) 규칙에서는 더 제한적인 작업(예: 사용자 재정의를 허용하지 않고 콘텐츠에 대한 액세스 제한)을 사용합니다.

![규칙 편집기에서 인스턴스 수입니다.](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)

### <a name="match-accuracy"></a>일치 정확도

위에서 설명한 것처럼, 중요한 정보 유형은 다양한 유형의 증거 결합을 통해 정의되고 검색됩니다. 일반적으로 중요한 정보 유형은 패턴이라는 이러한 여러 결합으로 정의됩니다. 증거가 덜 필요한 패턴은 일치 정확도(또는 신뢰 수준)가 낮은 데 반해 증거가 더 필요한 패턴은 일치 정확도(또는 신뢰 수준)가 높습니다. 모든 중요한 정보 유형에서 사용되는 실제 패턴 및 신뢰 수준에 대해 자세히 알아보려면 [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.

예를 들어 신용 카드 번호라는 중요한 정보 유형은 다음과 같은 두 개의 패턴으로 정의됩니다.

- 다음이 필요한 65% 신뢰의 패턴:

  - 신용 카드 번호 형식의 숫자

  - 체크섬을 전달하는 숫자

- 다음이 필요한 85% 신뢰의 패턴:

  - 신용 카드 번호 형식의 숫자

  - 체크섬을 전달하는 숫자

  - 올바른 형식의 키워드 또는 만료 날짜

규칙에서 이러한 신뢰 수준(또는 일치 정확도)을 사용할 수 있습니다. 일반적으로 일치 정확도가 낮은 규칙에서는 덜 제한적인 작업(예: 사용자 알림 보내기)을 사용합니다. 또한 일치 정확도가 높은 규칙에서는 더 제한적인 작업(예: 사용자 재정의를 허용하지 않고 콘텐츠에 대한 액세스 제한)을 사용합니다.

콘텐츠에서 특정 중요한 정보 유형(예: 신용 카드 번호)이 식별되면 하나의 신뢰 수준만 반환된다는 사실을 이해해야 합니다:

- 모든 일치 항목이 단일 패턴인 경우 해당 패턴의 신뢰 수준이 반환됩니다.

- 두 개 이상의 패턴에 대한 일치 항목이 있는 경우(즉, 서로 다른 두 가지 신뢰 수준의 일치 항목이 있는 경우) 모든 단일 패턴보다 높은 신뢰 수준만 반환됩니다. 이는 까다로운 부분입니다. 예를 들어 신용 카드의 경우 65% 패턴과 85% 패턴이 둘 다 일치하면 더 많은 증거가 더 높은 신뢰를 의미하므로 해당 중요한 정보 유형에 대해 반환되는 신뢰 수준은 90%보다 높습니다.

따라서 신용 카드에 대한 상호 배타적인 두 가지 규칙(65% 일치 정확도에 대한 규칙 하나와 85% 일치 정확도에 대한 규칙 하나)을 만들려는 경우 일치 정확도의 범위는 다음과 같습니다. 첫 번째 규칙에서는 65% 패턴의 일치 항목만 선택합니다. 두 번째 규칙에서는 **하나 이상의** 85% 일치 항목을 선택하며 다른 낮은 신뢰의 일치 항목이 **잠재적으로 있을 수 있습니다.**

![일치 정확도를 위해 범위가 서로 다른 두 개의 규칙](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)

해당 이유로 서로 다른 일치 정확도가 있는 규칙을 만들 때의 지침은 다음과 같습니다:

- 일반적으로 가장 낮은 신뢰 수준에서는 **최소** 와 **최대**(범위 아님)에 같은 값을 사용합니다.

- 일반적으로 가장 높은 신뢰 수준은 낮은 신뢰 수준 바로 위에서 100까지의 범위입니다.

- 일반적으로 그 사이에 있는 모든 신뢰 수준은 낮은 신뢰 수준 바로 위에서 높은 신뢰 수준 바로 아래까지의 범위입니다.

## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>보존 레이블을 DLP 정책의 조건으로 사용

DLP 정책에서 이전에 생성 및 게시 된 [보존 레이블](retention.md#retention-labels)을 조건으로 사용하는 경우 다음 사항에 유의해야 합니다.

- DLP 정책의 조건으로 사용하기 전 미리 보존 레이블을 작성 및 게시해야 합니다.
- 게시한 보존 레이블이 동기화되기까지 1일에서 7일까지 걸릴 수 있습니다. 자세한 내용은 보존 정책 형태로 게시되는 보존 레이블에 대한 [보존 레이블을 적용할 수 있게 되는 때](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) 및 자동 게시되는 보존 레이블에 대한 [보존 레이블이 유효해지는 데 걸리는 시간](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect)을 참조하세요.
- 정책** 형태로 보존 레이블 사용하기는 SharePoint 및 OneDrive***의 항목에 한해 지원됩니다.

  ![조건으로 레이블을 지정합니다.](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  보존 및 처리 중인 항목이 있고 다른 컨트롤을 적용하려는 경우 DLP 정책에 보존 레이블을 사용할 수 있습니다. 예를 들면 다음과 같습니다.

  - **과세 연도 2018** 이라는 보존 레이블을 게시했으며, 2018년에 과세 문서에 적용할 때 SharePoint에 저장된 10년 동안 보관한 다음 폐기합니다. 또한 DLP 정책으로 수행할 수 있는 항목을 조직 외부에서 공유하고 싶지 않습니다.

  > [!IMPORTANT]
  > DLP 정책에서 보존 레이블을 조건으로 지정하고 Exchange 및/또는 Teams를 위치로 포함하면 이 오류가 발생합니다. **"전자 메일 및 팀 메시지에서 레이블이 지정된 콘텐츠를 보호할 수 없습니다. 아래의 레이블을 제거하거나 Exchange 및 Teams를 위치로 사용하는 것을 중지하세요."** 이는 Exchange 전송에서 메시지 제출 및 배달이 진행되는 동안 레이블 메타 데이터를 평가하지 않기 때문입니다.

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a>민감도 레이블을 DLP 정책의 조건으로 사용

[DLP 정책에서](./dlp-sensitivity-label-as-condition.md) 민감도 레이블을 조건으로 사용하는 방법을 자세히 알아보습니다.

### <a name="how-this-feature-relates-to-other-features"></a>해당 기능이 다른 기능과 관련되는 방식

중요한 정보를 포함하는 콘텐츠에 다음과 같은 몇 가지 기능을 적용할 수 있습니다:

- [보존 레이블 및 보존 정책](retention.md) 모두 해당 콘텐츠에서 **보존** 작업을 적용할 수 있습니다.

- DLP 정책은 해당 콘텐츠에 **보호** 작업을 적용할 수 있습니다. 또한 이러한 작업을 적용하기 전에 DLP 정책은 레이블을 포함하는 콘텐츠 외에 다른 조건이 충족되도록 요구할 수 있습니다.

![중요한 정보에 적용할 수 있는 기능 다이어그램입니다.](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)

DLP 정책은 중요한 정보에 적용된 레이블 또는 보존 정책보다 풍부한 검색 기능을 갖습니다. DLP 정책은 중요한 정보를 포함하는 콘텐츠에 보호 작업을 적용할 수 있으며, 콘텐츠에서 중요한 정보가 제거되면 다음에 콘텐츠가 검색될 때 해당 보호 작업이 실행 취소됩니다. 그러나 중요한 정보를 포함하는 콘텐츠에 보존 정책 또는 레이블이 적용되면, 해당 적용은 중요한 정보가 제거되더라도 실행 취소되지 않는 일회성 작업입니다.

레이블을 DLP 정책에서 조건으로 사용하여 해당 레이블이 있는 콘텐츠에 보존 작업과 보호 작업을 둘 다 적용할 수 있습니다. 레이블을 포함하는 콘텐츠를 중요한 정보를 포함하는 콘텐츠와 정확히 같은 것으로 생각할 수 있습니다. 레이블 및 중요한 정보 유형은 콘텐츠에 작업을 적용할 수 있도록 해당 콘텐츠를 분류하는 데 사용되는 속성입니다.

![레이블을 조건으로 사용하는 DLP 정책 다이어그램입니다.](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)

## <a name="simple-settings-vs-advanced-settings"></a>간단한 설정과 고급 설정

DLP 정책을 생성할 때 간단한 설정과 고급 설정 중 하나를 선택하게 됩니다.

- **간단한 설정** 을 사용하면 규칙 편집기를 사용하여 규칙을 만들거나 수정하지 않고도 대부분의 일반적인 유형의 DLP 정책을 손쉽게 만들 수 있습니다.

- **고급 설정** 을 사용하면 규칙 편집기로 DLP 정책의 모든 설정을 제어할 수 있습니다.

걱정할 필요 없습니다. 간단한 설정과 고급 설정은 조건과 작업으로 구성된 규칙을 적용한다는 점에서 동일합니다. 간단한 설정에서는 규칙 편집기를 볼 수 없다는 점이 다릅니다. 간단한 설정을 사용하면 빠르고 간편하게 DLP 정책을 만들 수 있습니다.

### <a name="simple-settings"></a>간단한 설정

가장 일반적인 DLP 시나리오는 중요한 정보가 포함된 콘텐츠가 조직 밖의 사용자와 공유되지 않도록 보호하고, 콘텐츠에 액세스할 수 있는 사용자를 제한하거나, 최종 사용자 또는 관리자 알림을 발송하거나, 향후 조사를 위해 이벤트 감사를 수행하는 등의 자동 시정 조치를 취하는 정책을 만드는 것입니다. DLP는 중요한 정보가 우발적으로 공개되지 않도록 방지하는 데 사용됩니다.

DLP 정책을 만들 때 **간단한 설정 사용** 을 선택하면 이러한 목적을 간편하게 달성할 수 있습니다. 간단한 설정에서는 규칙 편집기를 사용하지 않고도 대부분의 일반적인 DLP 정책을 구현하는 데 필요한 모든 것을 사용할 수 있습니다.

![단순 및 고급 설정에 대한 DLP 옵션입니다.](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)

### <a name="advanced-settings"></a>고급 설정

사용자 지정 DLP 정책을 만들어야 하는 경우에는 **고급 설정 사용** 을 선택합니다.

고급 설정에서는 규칙 편집기를 사용하여 인스턴스 개수, 각 규칙의 일치 정확도(신뢰도 수준)를 비롯한 모든 옵션을 제어할 수 있습니다.

특정 장으로 건너뛰려면 규칙 편집기 상단의 탐색에 있는 항목을 클릭하여 해당 장으로 이동합니다.

![DLP 규칙 편집기 위쪽 탐색 메뉴](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)

## <a name="dlp-policy-templates"></a>DLP 정책 템플릿

DLP 정책을 생성하는 첫 번째 단계는 보호할 정보를 선택하는 것입니다. DLP 템플릿을 사용하여 새로운 규칙 집합을 처음부터 새로 작성하고 기본적으로 포함해야 하는 정보 유형을 고민하는 데 필요한 시간이 단축됩니다. 그런 다음 조직의 특정 요구 사항에 맞게 해당 요구 사항을 추가하거나 수정하여 규칙을 미세 조정할 수 있습니다.

미리 구성된 DLP 정책 템플릿은 HIPAA 데이터, PCI-DSS 데이터, 금융서비스 현대화법(Gramm-Leach-Bliley Act) 데이터 또는 고유 PII(개인 식별 정보)와 같은 특정 유형의 중요한 정보를 검색하는 데 도움이 될 수 있습니다. 일반적인 유형의 중요한 정보를 쉽게 찾아 보호할 수 있도록 하기 위해 Microsoft 365에 포함된 정책 템플릿에는 이미 시작하는 데 필요한 가장 일반적인 중요한 정보 유형이 포함되어 있습니다.

![미국 애국법용 템플릿에 중점을 두는 데이터 손실 방지 정책용 템플릿 목록입니다.](../media/791b2403-430b-4987-8643-cc20abbd8148.png)

조직에 고유한 요구 사항이 있을 경우 **사용자 지정 정책** 옵션을 선택하여 DLP 정책을 처음부터 새로 만들 수 있습니다. 사용자 지정 정책은 비어 있으며, 미리 구성된 규칙이 포함되어 있지 않습니다.

<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.

If you're creating DLP policies with a large potential impact, we recommend following this sequence:

1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.

2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.

3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.

    ![Options for using test mode and turning on policy.](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy.](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority.](../media/dlp-set-rule-priority.png)-->

## <a name="dlp-reports"></a>DLP 보고서

DLP 정책을 만들고 설정한 후에는 의도한 대로 작동하는지와 규정 준수 상태를 유지하는 데 도움이 되는지 확인할 수 있습니다. DLP 보고서를 사용하면 시간에 따른 DLP 정책 및 규칙 일치 수와 가양성 및 재정의 수를 빠르게 확인할 수 있습니다. 각 보고서에 대해 위치, 시간 프레임에 따라 일치하는 항목을 필터링할 수 있으며 특정 정책, 규칙 또는 작업으로 범위를 좁힐 수도 있습니다.

DLP 보고서를 사용하면 비즈니스 통찰력을 얻고 다음을 수행할 수 있습니다.

- 특정 기간에 초점을 맞추고 스파이크 및 추세의 이유를 이해합니다.

- 조직의 규정 준수 정책을 위반하는 비즈니스 프로세스를 검색합니다.

- DLP 정책이 비즈니스에 미치는 영향을 이해합니다.

또한 DLP 보고서를 사용하여 실행 중에 DLP 정책을 미세 조정할 수 있습니다.

![보안 및 준수 센터의 대시보드를 보고합니다.](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)

## <a name="how-dlp-policies-work"></a>DLP 정책이 작동하는 방식

DLP는 심도 깊은 콘텐츠 분석(단순 텍스트 검색 아님)을 사용하여 중요한 정보를 검색합니다. 이 심도 깊은 콘텐츠 분석은 키워드 일치, 사전 일치, 정규식 평가, 내부 함수 및 기타 방법을 사용하여 DLP 정책과 일치하는 콘텐츠를 검색합니다. 잠재적으로 데이터의 일부만 중요한 것으로 간주됩니다. DLP 정책은 나머지 콘텐츠로 작업하는 사람들에게 영향을 주거나 작업을 지연시키지 않으면서 해당 데이터를 식별 및 모니터링하고 자동으로 보호할 수 있습니다.

### <a name="policies-are-synced"></a>정책이 동기화됨

보안 &amp; 규정 준수 센터에서 DLP 정책을 만든 후 정책은 중앙 정책 저장소에 저장되며 다음을 포함하는 다양한 콘텐츠 원본과 동기화합니다:

- Exchange Online, 웹용 Outlook 및 Outlook.

- 비즈니스용 OneDrive 사이트.

- SharePoint Online 사이트.

- Office 데스크톱 프로그램 (Excel, PowerPoint 및 Word).

- Microsoft Teams 채널 및 채팅 메시지.

정책이 올바른 위치와 동기화된 후 콘텐츠를 평가하고 작업을 적용하기 시작합니다.
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->

### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>비즈니스용 OneDrive 및 SharePoint Online 사이트에서의 정책 평가

SharePoint Online 사이트 및 비즈니스용 OneDrive 사이트 전체에 걸쳐 문서는 지속적으로 변경됩니다. 즉 계속해서 생성되고, 편집되고, 공유됩니다. 즉, 문서는 언제든지 DLP 정책과 충돌을 일으키거나 정책을 준수할 수 있습니다. 예를 들어 한 사람이 자신의 팀 사이트에 중요한 정보를 포함하지 않는 문서를 업로드할 수 있습니다. 하지만 후에 다른 사람이 같은 문서를 편집하고 중요한 정보를 추가할 수 있습니다.

이러한 이유로 DLP 정책은 백그라운드에서 문서의 정책 일치 여부를 자주 확인합니다. 이러한 검사를 비동기 정책 평가로 간주할 수 있습니다.<!-- what is the frequency? looks like it is tied to the search crawl schedule -->

#### <a name="how-it-works"></a>작업 방법

사용자가 사이트에서 문서를 추가하거나 변경하면 검색 엔진에서 콘텐츠를 검색하여 나중에 검색할 수 있도록 합니다. 이 과정이 진행되는 동안 콘텐츠에 중요한 정보가 있는지 그리고 공유되고 있는지 검색합니다. 발견된 모든 중요한 정보는 검색 인덱스에 안전하게 저장되므로, 일반 사용자가 아닌 규정 준수 팀만 액세스할 수 있습니다. 사용자가 설정한 각 DLP 정책은 백그라운드에서(비동기적) 실행되며 정책과 일치하는 모든 콘텐츠를 자주 검색하고 부주의한 누설이 일어나지 않도록 방지하는 작업을 적용합니다.

![DLP 정책이 콘텐츠를 비동기적으로 평가하는 방법을 보여주는 다이어그램입니다.](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)

<!-- conflict with a DLP policy is bad wording --> 마지막으로 문서는 DLP 정책과 충돌할 수 있지만 DLP 정책을 준수할 수도 있습니다. 예를 들어 어떤 사람이 신용 카드 번호를 문서를 추가하는 경우 DLP 정책이 문서에 대한 액세스를 자동으로 차단할 수 있습니다. 하지만 나중에 이 사람이 중요한 정보를 제거하면 다음 번에 정책에 대해 문서가 평가될 때 작업(이 경우 차단)이 자동으로 실행 취소됩니다.

DLP는 인덱스를 지정할 수 있는 모든 콘텐츠를 평가합니다. 기본적으로 크롤링되는 파일 형식에 대한 자세한 내용은 [SharePoint Server의 크롤링되는 기본 파일 이름의 확장명 및 구문 분석되는 파일 형식](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)을 참고하십시오.

> [!NOTE]
> DLP 정책이 문서를 분석하기 전에 문서를 공유하지 못하게 하기 위해 콘텐츠가 인덱싱될 때까지 SharePoint 파일의 공유를 차단할 수 있습니다. 자세한 내용은 [신규 파일을 기본으로 민감하게 설정하기](/sharepoint/sensitive-by-default)를 참고하세요.

### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Exchange, Outlook 및 웹 상 Outlook의 정책 평가

Exchange Online을 위치로 포함 하는 DLP 정책을 만드는 경우 해당 정책은 Office 365 보안 &amp; 준수 센터에서 Exchange Online으로 동기화 된 후 Exchange Online에서 웹 상 Outlook 및 Outlook으로 동기화 됩니다.

Outlook에서 메시지를 작성할 때 생성 중인 콘텐츠가 DLP 정책을 기준으로 평가됨에 따라 사용자에게 정책 팁이 표시됩니다. 메시지가 발생하면 정상적인 메일 흐름의 일부로서 DLP 정책을 기준으로 평가되며, 이와 함께 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)과 Exchange 관리 센터에서 생성된 DLP 정책을 기준으로 평가됩니다. DLP 정책은 메시지와 첨부 파일을 모두 검색합니다.

### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Office 데스크톱 프로그램의 정책 평가

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel, PowerPoint 및 Word에는 중요한 정보를 식별하고 DLP 정책을 적용하는 SharePoint Online 및 비즈니스용 OneDrive와 동일한 기능이 있습니다. 해당 Office 프로그램은 중앙 정책 저장소에서 직접 해당 DLP 정책을 동기화한 후 사용자들이 DLP 정책에 포함된 사이트에서 연 문서로 작업할 때 DLP 정책을 기준으로 콘텐츠를 지속적으로 평가합니다.

Office의 DLP 정책 평가는 해당 콘텐츠를 사용하는 프로그램의 성능이나 사용자의 생산성에 영향을 미치지 않도록 고안되었습니다. 규모가 큰 문서에서 작업 중이거나 사용자의 컴퓨터가 다른 작업 중인 경우 정책 팁이 표시되는 데 몇 초 정도 걸릴 수 있습니다.

### <a name="policy-evaluation-in-microsoft-teams"></a>Microsoft Teams의 정책 평가
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

Microsoft Teams를 위치로 포함하는 DLP 정책을 만드는 경우 해당 정책은 Office 365 보안 &amp; 준수 센터에서 사용자 계정 및 Microsoft Teams 채널과 채팅 메시지와 동기화 됩니다. DLP 정책을 구성 하는 방법에 따라 제3자가 Microsoft Teams 채팅 또는 채널 메시지에서 중요한 정보를 공유하려고 시도하는 경우 메시지가 차단되거나 취소될 수 있습니다. 그리고 중요한 정보를 포함하고 게스트(외부 사용자)와 공유되는 문서가 해당 사용자에게 열리지 않습니다. 더 자세한 내용은 [데이터 손실 방지 및 Microsoft Teams](dlp-microsoft-teams.md)를 참고하십시오.

## <a name="permissions"></a>사용 권한

기본적으로 전역 관리자, 보안 관리자 및 규정 준수 관리자는 DLP 정책을 만들고 적용할 수 있습니다. DLP 정책을 만들 규정 준수 팀의 다른 구성원에게는 보안 및 준수 센터에 대한 &amp; 권한이 필요합니다. 기본적으로 테넌트 관리자는 이 위치에 액세스할 수 있으며, 규정 준수 관리자 및 기타 사용자에게 테넌트 관리자의 모든 권한을 부여하지 않고도 보안 및 준수 센터에 대한 액세스 권한을 부여할 &amp; 수 있습니다. 이렇게 하여 다음을 하는 것이 좋습니다.

1. Microsoft 365에서 그룹을 생성하고 규정 준수 책임자를 추가하십시오.

2. 보안 &amp; 준수 센터의 **사용 권한** 페이지에서 역할 그룹을 생성하십시오.

3. 역할 그룹을 만드는 동안 **역할 선택** 섹션을 사용하여 역할 그룹에 **DLP 준수 관리** 역할을 추가합니다.

4. **구성원 선택** 섹션을 사용하여 이전에 만든 Microsoft 365 그룹을 역할 그룹에 추가합니다.

**보기 전용 DLP 준수 관리** 역할을 부여하여 DLP 정책 및 DLP 보고서에 대한 보기 전용 권한이 있는 역할 그룹을 만들 수도 있습니다.

더 자세한 내용은 [Office 365 준수 센터 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참고하십시오.

이러한 정책은 DLP 정책을 만들고 적용하는 데만 필요합니다. 정책 적용을 위해서는 콘텐츠에 액세스하지 않아도 됩니다.

## <a name="find-the-dlp-cmdlets"></a>DLP cmdlet 찾기

대부분의 보안 &amp; 준수 센터용 cmdlet을 사용하려면 다음의 단계를 따르십시오:

1. [원격 PowerShell을 사용하여 Office 365 보안 &amp; 준수 센터에 연결](/powershell/exchange/connect-to-scc-powershell)

2. 이 [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection) 중 하나를 사용하십시오.

하지만 DLP 보고서에서는 Exchange Online을 포함한 Microsoft 365에서 데이터를 가져와야 합니다. 이러한 이유로 **DLP 보고서용 cmdlet은 보안 &amp; 준수 센터 Powershell이 아닌 Exchange Online Powershell에서 사용할 수 있습니다.** 따라서 DLP 보고서용 cmdlet을 사용하려면 다음의 단계가 필요합니다:

1. [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)합니다.

2. 다음과 같은 DLP 보고서용 cmdlet 중 하나 사용

    - [Get-DlpDetectionsReport](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [Get-DlpDetailReport](/powershell/module/exchange/Get-DlpDetailReport)

## <a name="more-information"></a>추가 정보

- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)

- [DLP 정책에 대한 알림을 보내고 정책 팁 표시](use-notifications-and-policy-tips.md)

- [FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기](protect-documents-that-have-fci-or-other-properties.md)

- [DLP 정책 템플릿에 포함되는 내용](what-the-dlp-policy-templates-include.md)

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)

- [DLP 함수가 찾는 항목](what-the-dlp-functions-look-for.md)

- [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)
