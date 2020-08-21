---
title: 위임된 관리 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 이 항목에서는 위임받은 Microsoft 365 관리 작업을 수행하려는 Microsoft 파트너 및 리더를 위한 FAQ와 답변을 제공합니다.
ms.openlocfilehash: 01781437bbc7e8fe5c035ea23e4392e734e0231f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827090"
---
# <a name="delegated-administration-faq"></a>위임된 관리 FAQ

이 항목에서는 다른 테넌트(회사)에 대한 EOP(Exchange Online Protection)를 관리하는 기능을 비롯하여 위임된 관리 작업을 수행하려는 Microsoft 파트너 및 리더를 위한 질문과 답변이 제공됩니다.

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>재판매인이고 고객의 테넌트를 관리해야 합니다. 어떻게 작동하나요?

Microsoft 파트너이거나 재판매인일 경우 Microsoft 관리자가 될 수 있도록 등록한 경우 사용 권한을 요청하여 관리 센터내에서 테넌트를 관리할 수 있습니다. 이를 위임된 관리하고 하며, 이를 통해 조직의 관리자인 것과 같이 Microsoft 365 테넌트(EOP 설정 포함)를 관리할 수 있습니다. 위임된 관리를 수행하는 단계는 다음과 같습니다.

1. [Microsoft Office 365 관리자](https://aka.ms/cloudbenefits)로 등록합니다.

2. 위임된 관리에 등록합니다. 고객의 계정을 관리할 수 있으려면 위임된 관리자로서 승인을 받아야 합니다. 승인을 받으려면 먼저 [위임된 관리를 위한 제안을 고객에게 보냅니다](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). 나중에 고객에게 위임된 관리를 제안할 수도 있습니다.

3. 구독 관리자 파트너 추가, 변경 또는 [삭제의 단계를 사용하여 위임된 관리 계정을 만듭니다.](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)

파트너 [방문: 위임된 관리 설정 방법에 대한 자세한 내용은](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) 비즈니스 및 파트너 구독 작성에 대한 자세한 내용을 제공합니다.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>재판매인이 아르는 고객입니다. 하위 테넌트를 위해 위임된 관리를 설정하려면 어떻게 합니까?

위임된 관리는 현재 재판매인 및 파트너만 사용할 수 있습니다. 그렇지만 하위 테넌트(회사)에 정책을 적용하는 데 도움이 되는 샘플 Windows PowerShell 스크립트를 제공해 드립니다. 자세한 내용은 [여러 테넌트에 EOP 설정을 적용하기 위한 샘플 스크립트](sample-script-for-applying-eop-settings-to-multiple-tenants.md)를 참조하세요.

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>하위 테넌트 관리자가 정책을 수정하지 못하게 하려면 어떻게 합니까?

Microsoft 365는 현재 이 기능을 지원하지 않습니다.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>모든 하위 테넌트의 보고를 통합하려면 어떻게 합니까?

관리하는 기사의 보고 기능 통합을 현재 Microsoft 365 관리 센터에서는 사용할 수 없습니다. 그러나 Microsoft Graph를 사용하여 이 작업을 수행할 [수 있습니다.](https://docs.microsoft.com/graph/overview)
