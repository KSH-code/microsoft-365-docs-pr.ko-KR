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
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 관리자는 Microsoft 파트너 및 대리점용 Microsoft 365의 위임된 관리 작업에 대한 질문과 대답을 볼 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 304fbba16d6c8e81e965462e3405824bd22982c9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405939"
---
# <a name="delegated-administration-faq"></a>위임된 관리 FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


이 문서에서는 Microsoft 파트너 및 대리점용 Microsoft 365의 위임된 관리 작업에 대한 질문과 대답을 제공합니다. 위임된 관리에는 다른 테넌트(회사)에 대한 EOP(Exchange Online Protection) 설정을 관리하는 기능도 포함되어 있습니다.

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>I'm a reseller and I need to manage my customer tenants. 이 방식은 어떻게 작동하나요?

Microsoft 파트너 또는 대리점인 경우 Microsoft 고문으로 등록한 경우 고객의 Microsoft 365 조직에서 위임된 관리 기능을 요청할 수 있습니다. 

위임된 관리를 사용하면 사용자가 해당 조직 내의 관리자인 경우처럼 Microsoft 365(EOP 설정 포함)를 관리할 수 있습니다. 위임된 관리 구성 단계는 다음 목록에 설명되어 있습니다.

1. [Microsoft Office 365 관리자](https://partner.microsoft.com/?cloudbenefits)로 등록합니다.

2. 위임된 관리에 등록합니다. 고객의 테넌트 관리가 시작되기 전에 위임된 관리자 권한으로 승인해야 합니다. 승인을 받으려면 먼저 [위임된 관리를 위한 제안을 고객에게 보냅니다](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). 나중에 고객에게 위임된 관리도 제공할 수 있습니다.

3. 구독 관리자 파트너 추가, 변경 또는 삭제의 단계를 사용하여 위임된 관리자 [계정을 만드세요.](../../admin/misc/add-partner.md)

위임된 관리 설정 방법에 대한 자세한 내용은 [파트너:](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) 비즈니스 구축 및 파트너 구독 관리하기를 방문하세요.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>I'm a customer, not a reseller. 하위텐트에 대해 위임된 관리자를 설정하는 방법

위임된 관리는 대리업체 및 파트너에게만 사용할 수 있습니다. 그러나 하위텐트(회사)에 정책을 적용하는 데 도움이 되는 샘플 PowerShell 스크립트가 있습니다. 자세한 내용은 [여러 테넌트에 EOP 설정을 적용하기 위한 샘플 스크립트](sample-script-for-applying-eop-settings-to-multiple-tenants.md)를 참조하세요.

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>하위 테 텐트 관리자가 내 정책을 수정하지 못하게 할 수 있나요?

아니요. Microsoft 365에는 현재 이 기능이 지원되지 않습니다.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>모든 하위텐트에서 통합 보고를 받을 수 있나요?

관리하는 회사 전체에서 보고를 통합하는 것은 Microsoft 365 관리 센터 보고서에서 사용할 수 없습니다. 그러나 Microsoft Graph를 사용하여 보고서를 볼 [수 있습니다.](https://docs.microsoft.com/graph/overview)
