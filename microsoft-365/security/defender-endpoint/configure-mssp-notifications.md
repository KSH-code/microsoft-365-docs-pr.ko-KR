---
title: MSSP로 전송된 경고 알림 구성
description: MSSP로 전송된 경고 알림 구성
keywords: 관리되는 보안 서비스 공급자, mssp, 구성, 통합
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d30bc5150277dd54a4a38dce8ac515d6be7dfb21
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208532"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>MSSP로 전송된 경고 알림 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> 이 단계는 MSSP 고객 또는 MSSP에서 수행될 수 있습니다. MSSP 고객을 대신하여 이를 구성하려면 MSSP에 적절한 사용 권한이 부여되어야 합니다.

포털에 액세스 권한이 부여되면 테넌트와 연결된 경고가 생성되어 조건을 설정할 때 전자 메일이 MSSP로 전송될 수 있도록 경고 알림 규칙을 만들 수 있습니다.

자세한 내용은 [경고 알림에 대한 규칙 만들기를 참조하세요.](configure-email-notifications.md#create-rules-for-alert-notifications)

이러한 확인란은 다음을 선택해야 합니다.

- **조직 이름 포함** - 고객 이름이 전자 메일 알림에 추가됩니다.
- **테넌트별** 포털 링크 포함 - 경고 링크 URL에는 대상 테넌트 포털에 직접 액세스할 수 있는 테넌트별 매개 변수(tid=target_tenant_id)가 있습니다.

## <a name="related-topics"></a>관련 항목

- [MSSP 액세스를 포털에 부여](grant-mssp-access.md)
- [MSSP 고객 포털에 액세스](access-mssp-portal.md)
- [고객 테넌트에서 경고 페치](fetch-alerts-mssp.md)
