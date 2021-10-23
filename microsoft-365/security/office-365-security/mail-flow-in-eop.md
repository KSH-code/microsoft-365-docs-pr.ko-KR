---
title: EOP의 메일 흐름
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(전자 메일 흐름)에서 메일 흐름 및 라우팅을 구성하는 옵션에 대해 Exchange Online Protection 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d7bca416a6144e2745a2c5d631c3e634e935ff4
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60554063"
---
# <a name="mail-flow-in-eop"></a>EOP의 메일 흐름

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 Exchange Online 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(독립 실행형 Exchange Online Protection) 조직에서는 조직으로 전송되는 모든 메시지가 작업자에게 표시되기 전에 EOP를 통과합니다. 처리를 위해 EOP를 통과하는 메시지를 작업자 받은 편지함으로 라우팅하기 전에 라우팅하는 방법에 대한 옵션이 있습니다.

## <a name="working-with-messages-and-message-access-options"></a>메시지 및 메시지 액세스 옵션 사용

EOP는 메시지를 라우팅하는 방법에 유연성을 제공합니다. 다음 항목에서 메일 흐름 프로세스의 단계에 대해 설명합니다.

[디렉터리 기반 Edge 차단을 사용하여](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 잘못된 받는 사람에게 보낸 메시지 거부 서비스 네트워크 경계에서 잘못된 받는 사람에 대한 메시지를 거부할 수 있는 디렉터리 기반 Edge 차단 기능에 대해 설명

[EOP에서](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 허용 도메인 보기 또는 편집에서는 EOP 서비스에 연결된 도메인을 관리하는 방법을 설명합니다.

조직에 하위 도메인을 추가한 경우 EOP 서비스를 통해 관리할 수도 있습니다. 하위 에 대한 자세한 내용은 [에서 하위](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)Exchange Online.

[커넥터를 사용하여](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 메일 흐름 구성 커넥터를 소개하고 커넥터를 사용하여 메일 라우팅을 사용자 지정하는 방법을 보여줍니다. 또한 파트너 조직과의 통신을 보호하고 스마트 호스트를 설정하는 시나리오를 소개합니다.

[EOP](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 전에 메일이 서비스 또는 장치로 라우팅되는 경우 커넥터를 구성하는 방법을 설명하는 향상된 커넥터 필터링

EOP가 전자 메일 사서함을 보호하는 하이브리드 환경에서는 Exchange 사서함에서 메일 흐름 규칙(전송 규칙)을 구성해야 Exchange. 이러한 메일 흐름 규칙은 사서함의 정크 메일 규칙이 메시지를 정크 메일 폴더로 이동할 수 있도록 EOP 스팸 필터링 판정을 변환합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 EOP 구성하기](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)를 참조하세요. 각 사용자의 정크 메일 폴더로 메시지를 이동하지 않을 경우 스팸 방지 정책(콘텐츠 필터 정책)을 편집하여 다른 작업을 선택할 수 있습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="verify-mail-flow"></a>메일 흐름 확인

커넥터 구성을 비롯하여 EOP 설정이 제대로 작동하는지 확인하려면 [EOP 서비스 설정](/exchange/standalone-eop/set-up-your-eop-service)에서 "작동 여부는 어떻게 확인합니까?" 섹션을 참조하세요.

[커넥터의 유효성을 검사하여](/exchange/mail-flow-best-practices/test-mail-flow) 메일 흐름 Microsoft 365 메일 흐름이 올바르게 설정되어 있는지 테스트하기 위한 지침을 제공합니다.
