---
title: MSSP Microsoft 365 Defender 포털에 액세스
description: MSSP Microsoft 365 Defender 포털에 액세스
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
ms.openlocfilehash: ed2322a602541f0144669f5567302bb8a603738d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187643"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>MSSP Microsoft 365 Defender 포털에 액세스

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> 이러한 단계 집합은 MSSP로 연결됩니다.

기본적으로 MSSP 고객은 다음 URL을 Microsoft 365 Defender 테넌트에 `https://securitycenter.windows.com/` 액세스합니다.

그러나 MSSP는 MSSP 고객 포털에 액세스하려면 다음과 같은 형식으로  `https://securitycenter.windows.com?tid=customer_tenant_id` 테넌트별 URL을 사용해야 합니다.

일반적으로 MSSP는 관리하려는 각 MSSP 고객의 Azure AD에 추가해야 합니다.

다음 단계에 따라 MSSP 고객 테넌트 ID를 얻은 다음 ID를 사용하여 테넌트 관련 URL에 액세스합니다.

1. MSSP로 자격 증명을 사용하여 Azure AD에 로그인합니다.

2. 디렉터리를 MSSP 고객의 테넌트로 전환합니다.

3. 속성 **Azure Active Directory > 선택합니다.** 디렉터리 ID 필드에서 테넌트 ID를 찾을 수 있습니다.

4. 다음 URL의 값을 바 사용하여 MSSP 고객 `customer_tenant_id` 포털에 `https://securitycenter.windows.com/?tid=customer_tenant_id` 액세스합니다. .

## <a name="related-topics"></a>관련 항목

- [MSSP 액세스를 포털에 부여](grant-mssp-access.md)
- [경고 알림 구성](configure-mssp-notifications.md)
- [고객 테넌트에서 경고 페치](fetch-alerts-mssp.md)
