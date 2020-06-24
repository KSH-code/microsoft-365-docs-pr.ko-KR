---
title: SEC Rule 17a-4를 준수하기 위해 Exchange Online과 보안 및 준수 센터 사용
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: CFTC 규칙 1.31(c)-(d), FINRA 규칙 4511, SEC 규칙 17a-4의 규정 요구 사항을 충족하도록 Exchange Online 및 규정 준수 센터 구성
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6dc53ec9dd016a2423ca96886bba400e2f17e17a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819078"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>SEC Rule 17a-4를 준수하기 위해 Exchange Online과 보안 및 준수 센터 사용

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.

However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.

이러한 조직이 보안 및 준수 센터가 Exchange online에 대한 규정 의무, 특히 규칙 17a-4 요구 사항을 충족하기 위해 어떻게 활용될 수 있는지 더 잘 이해할 수 있도록 Cohasset Associates와의 파트너십을 통해 평가를 발표했습니다.

Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.

## <a name="download-the-cohasset-assessment"></a>Cohasset 평가판 다운로드

[Cohasset 평가판을 여기에서 다운로드](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)할 수 있습니다.

![Cohasset Associates의 다운로드 가능한 평가의 제목 페이지](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>이 평가는 Exchange Online에만 적용됩니다.

Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.

It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>보존 잠금을 사용하는 것이 권장 구성의 핵심입니다.

Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:

- 보존 기간을 줄이면 보존할 수 있지만 보존 기간만 연장됩니다.
- 불변이란 필요한 보존 기간동안 해당 레코드를 덮어 쓰거나 지우거나 변경할 수 없음을 의미합니다.

In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.

By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:

- 정책의 보존 기간은 단축되지 않고 늘릴 수 있습니다.
- 사용자를 정책에 추가할 수는 있지만 사용자를 제거할 수는 없습니다.
- 보존 정책은 관리자가 삭제할 수 없습니다.

보존 잠금 장치는 SEC 17a-4 규정 요구사항을 충족하는 데 도움이 됩니다.

## <a name="how-to-set-up-preservation-lock"></a>보존 잠금을 설정하는 방법

PowerShell을 사용하여 보존 정책을 잠글 수 있습니다. 자세한 내용은 [보존 잠금을 사용하여 규정 요구 사항 준수](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)를 참조하세요.

## <a name="known-limitations"></a>알려진 제한

현재 Exchange Online에는 몇 가지 제한 사항이 있습니다.

- 팀 채팅 및 채널 메시지의 경우 스레드 통신을 사용할 수 없습니다.
- 팀 채팅 및 채널 메시지에 좋아요는 포함되어 있지 않습니다.

> [!NOTE]
> 이제 Microsoft 365 그룹 사서함에 대해 항목 수준 감사를 사용할 수 있습니다. 자세한 내용은 [사서함 감사 관리](enable-mailbox-auditing.md)를 참조하세요.
