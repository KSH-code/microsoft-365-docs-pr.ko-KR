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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection)에서 메일 흐름 및 라우팅 구성을 위한 옵션에 대해 알아볼 수 있습니다.
ms.openlocfilehash: e1c821e3de8dd7dd18c192522bd18fd32a395dca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200706"
---
# <a name="mail-flow-in-eop"></a>EOP의 메일 흐름

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 있는 Microsoft 365 조직이 나 Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직이 EOP를 통과 하기 전에 조직으로 전송 된 모든 메시지를 해당 사용자에 게 전달 합니다. EOP를 통과 하는 메시지를 처리 하기 위해 작업자의 받은 편지 함으로 라우팅되도록 하는 방법에 대 한 옵션을 사용할 수 있습니다.

## <a name="working-with-messages-and-message-access-options"></a>메시지 및 메시지 액세스 옵션 사용

EOP에서는 메시지의 라우팅 방식을 유연 하 게 제공 합니다. 다음 항목에서 메일 흐름 프로세스의 단계에 대해 설명합니다.

[디렉터리 기반 Edge 차단을 사용 하 여 잘못 된 받는 사람에 게 보낸 메시지 거부](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 서비스 네트워크 경계에서 잘못 된 받는 사람에 대 한 메시지를 거부할 수 있는 디렉터리 기반 Edge 차단 기능에 대해 설명 합니다.

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)에서는 EOP 서비스와 연결된 도메인을 관리하는 방법을 설명합니다.

조직에 하위 도메인을 추가한 경우 EOP 서비스를 통해 관리할 수도 있습니다. 하위 도메인에 대 한 자세한 내용은 [Exchange Online에서 하위 도메인에 대 한 메일 흐름 사용](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)을 참고 하세요.

[커넥터를 사용 하 여 메일 흐름 구성](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 커넥터를 도입 하 고 메일 라우팅을 사용자 지정 하는 데 사용할 수 있는 방법을 보여 줍니다. 또한 파트너 조직과의 통신을 보호하고 스마트 호스트를 설정하는 시나리오를 소개합니다.

[커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) EOP 전에 메일이 서비스 또는 장치로 라우팅되는 경우 커넥터를 구성 하는 방법을 설명 합니다.

독립 실행형 EOP 조직에서는 정크 메일이 각 사용자의 정크 메일 폴더로 올바르게 라우팅되도록 하기 위해 몇 가지 구성 단계를 수행 해야 합니다. [하이브리드 환경의 정크 메일 폴더에 스팸을 배달 하도록 독립 실행형 EOP 구성](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)에 자세히 설명 되어 있습니다. 각 사용자의 정크 메일 폴더로 메시지를 이동 하지 않으려면 스팸 방지 정책 (콘텐츠 필터 정책이 라고도 함)을 편집 하 여 다른 작업을 선택할 수 있습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="verify-mail-flow"></a>메일 흐름 확인

커넥터 구성을 비롯하여 EOP 설정이 제대로 작동하는지 확인하려면 [EOP 서비스 설정](set-up-your-eop-service.md)에서 "작동 여부는 어떻게 확인합니까?" 섹션을 참조하세요.

[메일 흐름 테스트 Microsoft 365 커넥터를 확인 하 여](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) 메일 흐름이 올바르게 설정 되었는지 테스트 하는 지침을 제공 합니다.
