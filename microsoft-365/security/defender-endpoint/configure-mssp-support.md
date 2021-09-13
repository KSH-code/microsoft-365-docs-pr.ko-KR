---
title: 관리되는 보안 서비스 공급자 지원 구성
description: 끝점용 Microsoft Defender와 MSSP 통합을 구성하는 데 필요한 단계 수행
keywords: 관리되는 보안 서비스 공급자, mssp, 구성, 통합
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 52b0b9b69ce81174f346cd2c8d3d6a50c1e231ca
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222941"
---
# <a name="configure-managed-security-service-provider-integration"></a>관리형 보안 서비스 공급자 통합 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

관리되는 보안 서비스 공급자(MSSP) 통합을 사용하도록 설정하려면 다음 구성 단계를 수행해야 합니다.

> [!NOTE]
> 이 문서에서는 서비스 공급자와 서비스 소비자를 구분하기 위해 다음 용어를 사용합니다.
>
> - MSSP: 조직의 보안 장치를 모니터링하고 관리하기 위한 보안 조직입니다.
> - MSSP 고객: MSSP의 서비스를 참여하는 조직.

통합을 통해 MSSP는 다음 작업을 수행할 수 있습니다.

- MSSP 고객의 사이트 포털에 Microsoft 365 Defender 액세스
- 전자 메일 알림 및
- SIEM(보안 정보 및 이벤트 관리) 도구를 통해 경고 페치

MSSP에서 이러한 작업을 수행하려면 MSSP 고객이 MSSP가 포털에 액세스할 수 있도록 끝점 테넌트에 대한 Defender에 대한 액세스 권한을 부여해야 합니다.

일반적으로 MSSP 고객은 초기 구성 단계를 수행하여 MSSP에 보안 중앙 테넌트에 Windows Defender 권한을 부여합니다. 액세스 권한이 부여된 후 다른 구성 단계는 MSSP 고객 또는 MSSP에서 수행될 수 있습니다.

일반적으로 다음 구성 단계를 수행해야 합니다.

- **MSSP에 액세스 권한을 Microsoft 365 Defender**

  이 작업은 MSSP 고객이 수행해야 합니다. 끝점 테넌트에 대한 MSSP 고객의 Defender 액세스 권한을 MSSP에 부여합니다.

- **MSSP로 전송된 경고 알림 구성**

  이 작업은 MSSP 고객 또는 MSSP에서 수행될 수 있습니다. 이를 통해 MSSP는 MSSP 고객을 위해 해결해야 하는 경고를 알 수 있습니다.

- **MSSP 고객의 테넌트에서 SIEM 시스템으로 경고 페치**

  이 작업은 MSSP에서 수행됩니다. 이를 통해 MSSP는 SIEM 도구에서 경고를 페치할 수 있습니다.

- **API를 사용하여 MSSP 고객의 테넌트에서 경고 페치**

  이 작업은 MSSP에서 수행됩니다. 이를 통해 MSSP는 API를 사용하여 경고를 페치할 수 있습니다.

## <a name="multi-tenant-access-for-mssps"></a>MSSP에 대한 다중 테넌트 액세스

다중 테넌트 위임된 액세스를 구현하는 방법에 대한 자세한 내용은 관리되는 보안 서비스 공급자에 대한 다중 테넌트 [액세스를 참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)

## <a name="related-topics"></a>관련 항목

- [MSSP 액세스를 포털에 부여](grant-mssp-access.md)
- [MSSP 고객 포털에 액세스](access-mssp-portal.md)
- [경고 알림 구성](configure-mssp-notifications.md)
- [고객 테넌트에서 경고 페치](fetch-alerts-mssp.md)
