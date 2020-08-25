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
description: 관리자는 microsoft 파트너 및 대리점에 대해 Microsoft 365의 위임 된 관리 작업에 대 한 질문과 대답을 볼 수 있습니다.
ms.openlocfilehash: 3efadc8793778bfabe10922e8e29044747d60ad0
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866698"
---
# <a name="delegated-administration-faq"></a>위임된 관리 FAQ

이 문서에서는 microsoft 파트너 및 대리점 용 Microsoft 365의 위임 된 관리 작업에 대 한 질문과 대답을 제공 합니다. 위임 된 관리에는 다른 테 넌 트 (회사)에 대 한 EOP (Exchange Online Protection) 설정을 관리 하는 기능이 포함 되어 있습니다.

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>대리점 이며, 고객 테 넌 트를 관리 해야 합니다. 작동 방식

Microsoft 파트너 또는 대리점이 고 Microsoft advisor에 등록 한 경우 고객의 Microsoft 365 조직에서 _위임 된 관리_ 기능을 요청할 수 있습니다.

위임 된 관리를 사용 하면 해당 조직 내의 관리자 인 것 처럼 Microsoft 365 (EOP 설정 포함)를 관리할 수 있습니다. 위임 된 관리를 구성 하는 단계는 다음 목록에 설명 되어 있습니다.

1. [Microsoft Office 365 관리자](https://aka.ms/cloudbenefits)로 등록합니다.

2. 위임 된 관리에 등록 합니다. 고객의 테 넌 트를 관리 하려면 먼저 사용자에 게 위임 된 관리자로 권한을 부여 해야 합니다. 승인을 받으려면 먼저 [위임된 관리를 위한 제안을 고객에게 보냅니다](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). 나중에 고객에 게 위임 된 관리를 제공할 수도 있습니다.

3. [구독 관리자 파트너 추가, 변경 또는 삭제](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)의 단계를 사용 하 여 위임 된 관리자 계정을 만듭니다.

위임 된 관리를 설정 하는 방법에 대 한 자세한 내용은 [파트너: 비즈니스 구축 및 파트너 구독 관리](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) 를 참조 하세요.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>저는 대리점이 아니라 고객입니다. 하위 테 넌 트에 대해 위임 된 관리자를 설정 하려면 어떻게 해야 하나요?

위임 된 관리는 리셀러 및 파트너만 사용할 수 있습니다. 그러나 하위 테 넌 트 (회사)에 정책을 적용 하는 데 도움이 되는 샘플 PowerShell 스크립트가 있습니다. 자세한 내용은 [여러 테넌트에 EOP 설정을 적용하기 위한 샘플 스크립트](sample-script-for-applying-eop-settings-to-multiple-tenants.md)를 참조하세요.

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>하위 테 넌 트 관리자가 내 정책을 수정 하지 못하게 할 수 있나요?

아니요. Microsoft 365는 현재이 기능을 제공 하지 않습니다.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>모든 하위 테 넌 트에 대해 보고 기능을 통합할 수 있나요?

관리 하는 회사 전체의 통합 보고 기능을 Microsoft 365 관리 센터 보고서에서는 사용할 수 없습니다. 그러나 [Microsoft Graph](https://docs.microsoft.com/graph/overview)를 사용 하 여 보고서를 볼 수는 있습니다.
