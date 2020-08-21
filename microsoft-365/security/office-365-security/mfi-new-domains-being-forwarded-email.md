---
title: 전자 메일 인사이트가 전달되는 새 도메인
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 관리자는 최신 Exchange 관리 센터에서 전달되는 새 도메인을 사용하여 조직의 사용자가 전원을 방해 받지 않은 외부 도메인으로 메시지를 전달하는 경우 조사하는 방법을 볼 수 있습니다.
ms.openlocfilehash: 0b4cd0490feebc8e05deb889b3cf54e1ea9f5928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826932"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>보안 도메인 준수 센터에서 전달되는 새 & 구성

특정 도메인의 외부 받는 사람에게 전자 메일 메시지를 전달해야 하는 유효한 업무상의 이유가 있을 수 있지만, 조직의 사용자가 외부 도메인으로의 메시지 전달을 신중하게 시작하고 조직의 어떤 사람도 외부 도메인으로 메시지를 전달한 것이 라고 의심이 있습니다. (새 도메인) 이 조건은 사용자 계정이 위제됨을 나타일 수 있습니다. 계정이 손상되었다고 의심되는 경우 [손상된 이메일 계정에 대한 응답을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)

전달되는 **전자 메일 인사이트인** 새 도메인은 조직의 사용자가 새 도메인으로 메시지를 전달하고 있을 때 알아줍니다.

이 인사이트는 문제가 검색될 때만 나타나며 전달 보고서 [페이지에 표시됩니다.](view-mail-flow-reports.md#forwarding-report)

![전자 메일 인사이트가 전달되는 새 도메인](../../media/mfi-new-domains-being-forwarded.png)

위로 를 클릭하면 전달 보고서로 의대한 링크를 비롯하여 전달된 메시지에 대한 자세한 내용을 찾을 수 있는 플라이 [아웃이 표시됩니다.](view-mail-flow-reports.md#forwarding-report)

![전달되는 새 도메인을 클릭한 후 표시되는 세부 플라이아웃](../../media/mfi-new-domains-being-forwarded-details.png)

또한 상위 인사이트 보기 영역(보고서 대시보드 또는)에서 **View all** **모든 정보 보기를 클릭하면 이 & 세부 정보 페이지에** **나타나도록** \> **할 수** <https://protection.office.com/insightdashboard> 있습니다.

외부 도메인으로 자동 메시지를 전달하지 않도록 하려면 일부 또는 전체 외부 도메인에 대한 원격 도메인을 구성합니다. 자세한 내용은 [Exchange Online에서 원격 도메인 관리를 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)
