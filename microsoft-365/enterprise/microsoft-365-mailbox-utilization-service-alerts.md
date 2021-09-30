---
title: 사서함 사용률 서비스 경고
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: admindeeplinkMAC
f1.keywords:
- NOCSH
description: 사서함 사용률 서비스 알림을 사용하여 사서함 할당량에 도달하는 보류된 사서함을 모니터링합니다.
ms.openlocfilehash: 32536cf8a034867ecb82e44487f34280a9b591ac
ms.sourcegitcommit: f9e038dd8420e7af2d1b0244d3567b376475c641
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011467"
---
# <a name="service-alerts-for-mailbox-utilization-in-exchange-online-monitoring"></a>Exchange Online 모니터링의 사서함 사용률에 대한 서비스 알림

할당량에 도달하거나 초과할 위험이 있는 Exchange Online 사서함을 알리는 새로운 Exchange Online 서비스 알림을 릴리스했습니다. 이러한 서비스 경고는 관리자 개입이 필요할 수 있는 조직의 사서함 수에 대한 가시성을 제공합니다.

이러한 서비스 알림은 알림 Microsoft 365 관리 센터. 이러한 서비스 알림을 보려면 상태 서비스 상태 Exchange Online 활성 문제  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank"></a>  >   **탭을** 클릭합니다. 사서함 사용률 서비스 경고의 예는 다음과 같습니다.

:::image type="content" alt-text="사서함 사용률 서비스 경고입니다." source="../media/MailboxUtilizationServiceAlert.png" lightbox="../media/MailboxUtilizationServiceAlert.png":::

저장소 할당량(사서함 사용 현황 보고서)에 가까운 사서함 목록을 표시하려면 다음 스크린샷에서 강조 표시된 링크를 클릭합니다. 이 링크는 서비스 경고에 표시됩니다.

:::image type="content" alt-text="사서함 사용 현황 보고서에 연결합니다." source="../media/LinkToMailboxUsageReport.png" lightbox="../media/LinkToMailboxUsageReport.png":::

또는 사서함 사용 현황 보고서에 대한 직접 URL은 <https://admin.microsoft.com/Adminportal/Home?source=applauncher#/reportsUsage/MailboxUsage> 입니다.

## <a name="what-do-these-service-alerts-indicate"></a>이러한 서비스 알림이 나타내는 것은 무엇입니까?

사서함 사용률에 대한 서비스 알림은 사서함 저장소 할당량에 가까운 보류된 사서함에 대해 관리자에게 알릴 수 있습니다. 사서함에 배치할 수 있는 보존 유형에는 소송 보존, eDiscovery 보류 및 Microsoft 365 보존 정책(데이터를 보존하도록 구성)이 포함됩니다. 사서함이 보류 중이면 사용자(또는 자동화된 프로세스)는 사서함에서 데이터를 영구적으로 제거할 수 없습니다. 대신 관리자는 사용자의 기본 사서함에서 보관 사서함으로 데이터를 이동하도록 Exchange Online(조직의 규정 준수 정책과 관련된 조직의 준수 정책에 따라)에서 MRM 보존 정책을 구성해야 합니다. 그렇지 않은 경우 보류의 사서함이 위험 또는 경고 상태가 [](../compliance/enable-archive-mailboxes.md) 될 경우 [](../compliance/enable-autoexpanding-archiving.md) 관리자는 보관 사서함을 사용하도록 설정하고 자동 확장 보관을 사용하도록 설정한 다음 사서함에 할당된 보관 정책(기본 사서함에서 보관 사서함으로 전자 메일을 이동)의 보존 기간이 충분히 짧아야 합니다. 사서함 사용률 서비스 경고로 식별되는 할당량 문제를 해결하기 위해 아무 것도 수행되지 않으면 사용자가 전자 메일 메시지 또는 모임 초대를 보내거나 받지 못하게 될 수 있습니다.

사서함 사용률에 대한 서비스 알림에는 할당량에 가까운 사서함 수에 대한 표가 포함되어 있습니다. 다음 섹션에서는 이러한 테이블의 정보와 이러한 사서함이 할당량 초과되지 않도록 관리자가 취할 수 있는 조치에 대해 설명합니다.

> [!NOTE]
> 서비스 알림에는 다음 섹션에 설명된 표의 열에 나타나는 사서함 할당량 속성에 대한 설명이 포함됩니다.

### <a name="mailboxes-on-hold-without-an-archive"></a>보관함이 없는 보류된 사서함

다음 표에는 할당량에 가까운 보류 중이지만 보관 사서함을 사용할 수 없는 보류된 사서함 수가 나열되어 있습니다. 표의 각 열은 특정 할당량과 해당 할당량에 가까운 사서함 수를 식별합니다.

| # Mailboxes ProhibitSendReceiveQuota(경고)| # Mailboxes ProhibitSendReceiveQuota (Critical)** |# Mailboxes RecoverableItemsQuota(경고)|# Mailboxes RecoverableItemsQuota (Critical)** |
|:--------------|:--------------|:------------------|:--------------- |
| 2             | 2             | 1                 | 0               |
||||

이러한 사서함에 대해 관리자가 취할 수 있는 작업은 보관 사서함을 사용하도록 설정하고 항목을 보관 사서함으로 이동하는 MRM 보관 정책(Exchange Online 사서함으로 항목을 이동하는 MRM 보존 정책)이 사서함에 적용되도록 하는 것입니다. 자세한 내용은 사서함에 대한 보관 및 삭제 정책 설정 [을 참조하세요.](../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)

보관 사서함을 사용하도록 설정한 후 복구 가능한 항목 폴더에 대한 할당량 증가를 고려하는 것이 좋습니다. 이렇게 하면 보류된 사서함의 복구 가능한 항목 폴더 할당량 초과를 방지할 수 있습니다. 자세한 내용은 보류된 사서함에 대한 복구 가능한 항목 [할당량 늘리기 를 참조하세요.](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)

### <a name="mailboxes-on-hold-with-an-archive"></a>보관함이 있는 보류된 사서함

다음 표에는 할당량에 가까운 보류 중 보관 사서함이 사용하도록 설정된 사서함 수가 나열되어 있습니다.

|# Mailboxes ProhibitSendReceiveQuota(경고) |# Mailboxes ProhibitSendReceiveQuota(중요) |# Mailboxes RecoverableItemsQuota(경고) |# Mailboxes RecoverableItemsQuota (Critical)** |
|:--------------|:--------------|:------------------|:--------------- |
| 1             | 1             | 6                  | 0               |
||||

이러한 사서함에 대해 관리자가 취할 수 있는 작업은 복구 가능한 항목 폴더의 할당량 증가입니다. 자세한 내용은 보류된 사서함에 대한 복구 가능한 항목 [할당량 늘리기 를 참조하세요.](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)

또한 관리자는 항목을 보관 사서함으로 이동하는 MRM 보관 정책이 사서함에도 적용되고 보관 정책의 보존 기간이 충분히 짧아서 항목이 보관 사서함으로 이동되기 전에 기본 사서함에 너무 오래 보존되지 않는지도 확인해야 합니다.

> [!NOTE]
> 또한 MRM 보관 정책은 기본 사서함의 복구 가능한 항목 폴더에서 해당 보관 사서함의 복구 가능한 항목 폴더로 항목을 이동합니다. 이 기능은 사서함이 복구 가능한 항목 할당량에 대한 할당량 초과를 방지하는 데 도움이 됩니다.

### <a name="mrm-retention-policies-in-your-organization"></a>조직의 MRM 보존 정책

사서함 사용률에 대한 서비스 알림에는 조직의 MRM 보존 정책 및 보존 정책인 사서함에 보관 사서함이 있는지 여부에 대한 정보가 포함된 표가 포함될 수도 있습니다. 보존 정책에 대한 자세한 내용은 에서 보존 태그 및 보존 [정책을 Exchange Online.](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

| RetentionPolicyGuid | MailboxType | HasMoveDumpsterToArchiveTag | HasMovePrimaryToArchiveTag | HasPersonalArchiveTag |  사서함 |
|:--------------|:--------------|:---------------|:---------------|:---------------|:--------------- |
| 6c041498-1611-5011-a058-1156ce60890c | PrimaryWithArchive | True | 거짓 | True | 398 |
| 6c041498-1611-5011-a058-1156ce60890c | Primary | True | 거짓 | True | 10  |
| 749ceecc-d49d-4000-a9d5-594dbaea1e56 | PrimaryWithArchive | False | True | 거짓 | 7  |
| 269f6a85-1234-4648-8cde-59bbc7bc67d0 | PrimaryWithArchive | True | True | True | 1 |
| 13fb778d-e1cb-4c44-5768-ad4282906c1f | PrimaryWithArchive | True | True  | 거짓 | 1 |
|||||||

다음 목록에서는 이전 표의 각 열에 대해 설명합니다.

- **RetentionPolicyGuid**: 조직의 사서함에 할당된 보존 정책의 GUID입니다. 이전 예에서는 동일한 보존 정책에 대해 두 개의 별도 행이 있습니다. 첫 번째 행은 정책이 할당된 보관 사서함의 수를 나타냅니다. 두 번째 행은 동일한 정책이 할당된 보관함이 없는 사서함 수를 나타냅니다.

   이 열에 나열된 보존 정책에 대한 자세한 정보를 얻습니다. PowerShell 에서 [Exchange Online 실행합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-RetentionPolicy <GUID> | FL
   ```

   **Name** 속성 값은 Exchange 관리 센터의 보존 정책 페이지에  표시되는 보존 정책의 이름입니다.

- **MailboxType**: 정책이 할당된 사서함의 유형을 지정합니다. 값에는 *Primary(보관* 사서함이 없는 사서함) 또는 *PrimaryWithArchive(보관* 사서함이 있는 사서함)가 포함됩니다. 이 열의 값이 *Primary인* 경우 정책이 할당된 사서함에  대해 보관 사서함을 사용하도록 설정해야 합니다(사서함 열은 이러한 사서함 수를 나타임). 그렇지 않으면 항목을 이동할 보관함이 아니기 때문에 보관 정책 또는 개인 보관 태그가 작동하지 않습니다.

- **HasMoveDumpsterToArchiveTag:** 보존 정책에 보관 사서함의 복구 가능한 항목 폴더에 있는 항목을 보관 사서함의 복구 가능한 항목 폴더로 이동하는 보존 태그가 포함되어 있습니다. 이 유형의 보존 태그는 관리자가 설정합니다. 복구 가능한 항목 태그의 보존 기간이 너무 긴 경우 보존 기간을 줄이면 사서함이 복구 가능한 항목 폴더의 할당량에 가까운 것을 방지하는 데 도움이 됩니다. 예를 들어 보존 기간을 30일로 설정하면 3~5일로 줄이는 것이 도움이 될 수 있습니다.  자세한 내용은 보류된 사서함에 대한 복구 가능한 항목 [할당량 늘리기 를 참조하세요.](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)

- **HasMovePrimaryToArchiveTag:** 보존 정책에 포함된 기본 "보관함으로 이동" 보존 태그(보관 정책이라고도함)가 포함되어 있는 경우를 나타냅니다. 이 경우 메시지는 기본 사서함의 일반 폴더에서 보관 사서함으로 이동됩니다. 이 유형의 보존 태그는 관리자가 설정합니다. 이 태그의 보존 기간이 너무 짧을 경우 사용자는 계속해서 기본 사서함의 할당량에 도달하는 데 문제가 있을 수 있습니다. 보관 정책의 보존 기간을 줄이면 이 문제를 해결하는 데 도움이 될 수 있습니다.

- **HasPersonalArchiveTag:** 보존 정책에 개인 "보관함으로 이동" 태그가 포함되어 있는지 나타냅니다. 보존 정책에 개인 "보관함으로 이동" 태그가 포함되어 있는 경우 사용자는 사서함의 폴더 및 메시지에 이 태그를 적용하여 항목을 보관함으로 이동할 수 있습니다. 사용자는 이 태그가 적용된 폴더로 메시지를 이동하는 받은 편지함 규칙을 설정할 수도 있습니다. 두 경우 모두 항목을 보관함으로 이동하면 기본 사서함의 할당량에 도달하지 않도록 할 수 있습니다.

- **사서함:** 보존 정책이 할당된 사서함 **수(MailboxType** 열에 표시된 보관함이 있는 사서함 또는 보관함이 없는 사서함)를 나타냅니다.

## <a name="how-often-will-i-see-these-service-alerts"></a>이러한 서비스 경고는 얼마나 자주 표시하나요?

할당량 문제를 해결하기 위해 조치를 취하지 않으면 4일마다 이 유형의 서비스 경고가 표시될 수 있습니다. 후속 서비스 알림에는 할당량에 가까운 다른 사서함의 사서함 수가 더 높을 수 있습니다. 할당량 문제를 해결하기 위한 조치를 취하는 경우 이 서비스 알림은 할당량 문제가 있는 다른 사서함이 식별된 경우만 발생합니다.

## <a name="more-information"></a>추가 정보

- 보관 사서함 문제 해결 및 해결에 대한 자세한 내용은 Microsoft 365 [준수 문제 해결을 참조하세요.](/office365/troubleshoot/microsoft-365-compliance-welcome)

- 사서함에 배치된 보류를 식별하는 방법에 대한 지침은 사서함에 배치된 보류 유형을 식별하는 [방법을 참조하세요.](../compliance/identify-a-hold-on-an-exchange-online-mailbox.md)
