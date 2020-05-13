---
title: 위임된 관리 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 이 항목에서는 위임 된 Microsoft 365 관리 작업을 수행 하려는 Microsoft 파트너 및 대리점에 대 한 Faq 및 답변을 제공 합니다.
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209526"
---
# <a name="delegated-administration-faq"></a>위임된 관리 FAQ

이 항목에서는 다른 테 넌 트 (회사)에 대 한 EOP (Exchange Online Protection)를 관리 하는 기능을 비롯 하 여 위임 된 관리 작업을 수행 하려는 Microsoft 파트너 및 대리점에 대 한 질문과 대답이 제공 됩니다.

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>저는 대리점 이며, 고객의 테 넌 트를 관리 해야 합니다. 작동 방식

Microsoft 파트너 또는 대리점이 고 Microsoft advisor에 등록 한 경우 관리 센터에서 테 넌 트를 관리 하는 권한을 요청할 수 있습니다. 이를 위임 된 관리 라고 하며, 조직 내의 관리자 인 것 처럼 Microsoft 365 테 넌 트 (EOP 설정 포함)를 관리할 수 있습니다. 위임된 관리를 수행하는 단계는 다음과 같습니다.

1. [Microsoft Office 365 관리자](https://aka.ms/cloudbenefits)로 등록합니다.

2. 위임 된 관리에 등록 합니다. 고객의 계정을 관리할 수 있으려면 위임된 관리자로서 승인을 받아야 합니다. 승인을 받으려면 먼저 [위임된 관리를 위한 제안을 고객에게 보냅니다](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). 나중에 고객에게 위임된 관리를 제안할 수도 있습니다.

3. [구독 관리자 파트너 추가, 변경 또는 삭제](https://docs.microsoft.com/office365/admin/misc/add-partner)의 단계를 사용 하 여 위임 된 관리자 계정을 만듭니다.

위임 된 관리를 설정 하는 방법에 대 한 자세한 내용은 [파트너: 비즈니스 구축 및 파트너 구독 관리](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) 를 참조 하세요.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>대리점, 내 테 넌 트에 대 한 위임 된 관리자를 설정 하는 방법은 무엇입니까?

위임된 관리는 현재 재판매인 및 파트너만 사용할 수 있습니다. 그렇지만 하위 테넌트(회사)에 정책을 적용하는 데 도움이 되는 샘플 Windows PowerShell 스크립트를 제공해 드립니다. 자세한 내용은 [여러 테넌트에 EOP 설정을 적용하기 위한 샘플 스크립트](sample-script-for-applying-eop-settings-to-multiple-tenants.md)를 참조하세요.

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>하위 테넌트 관리자가 정책을 수정하지 못하게 하려면 어떻게 합니까?

Microsoft 365는 현재이 기능을 제공 하지 않습니다.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>모든 하위 테넌트의 보고를 통합하려면 어떻게 합니까?

지금 Microsoft 365 관리 센터 보고서에 대해 관리 하는 회사 전체의 통합 보고 기능을 사용할 수 없습니다. 그러나 [Microsoft Graph](https://docs.microsoft.com/graph/overview)를 사용 하 여이 작업을 수행할 수 있습니다.
