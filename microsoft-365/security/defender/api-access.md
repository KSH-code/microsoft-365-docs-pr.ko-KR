---
title: MICROSOFT 365 DEFENDER API에 액세스
description: 앱 API에 액세스하는 Microsoft 365 Defender 방법 학습
keywords: 액세스, api, 응용 프로그램 컨텍스트, 사용자 컨텍스트, aad 응용 프로그램, 액세스 토큰
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3cbd329c63d7cf1868083c66919773e14ed51156
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220115"
---
# <a name="access-the-microsoft-365-defender-apis"></a>MICROSOFT 365 DEFENDER API에 액세스

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

Microsoft 365 Defender API 집합을 통해 많은 데이터와 작업을 노출합니다. 이러한 API를 사용하면 워크플로를 자동화하고 워크플로의 기능을 Microsoft 365 Defender 사용할 수 있습니다.

일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.

- 응용 Azure Active Directory 만들기
- 이 응용 프로그램을 사용하여 액세스 토큰 얻기
- 토큰을 사용하여 Microsoft 365 Defender API에 액세스

> [!NOTE]
> API 액세스에는 OAuth2.0 인증이 필요합니다. 자세한 내용은 [OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

이러한 단계를 완료하면 특정 컨텍스트를 사용하여 Microsoft 365 Defender API에 액세스할 수 있습니다.

## <a name="application-context-recommended"></a>응용 프로그램 컨텍스트(권장)

백그라운드 서비스 또는 데몬과 같이 로그인한 사용자가 없는 실행된 앱에 대해 이 컨텍스트를 사용하세요.

1. 웹 Azure Active Directory 만들 수 있습니다.
2. 응용 프로그램에 원하는 사용 권한을 할당합니다.
3. 응용 프로그램에 대한 키를 생성합니다.
4. 응용 프로그램 및 해당 키를 사용하여 보안 토큰을 얻습니다.
5. 토큰을 사용하여 API에 Microsoft 365 Defender 있습니다.

자세한 내용은 사용자 없이 앱 만들기를 **[Microsoft 365 Defender 참조하세요.](api-create-app-web.md)**

## <a name="user-context"></a>사용자 컨텍스트

이 컨텍스트를 사용하여 단일 사용자를 대신하여 작업을 수행할 수 있습니다.

1. 기본 Azure Active Directory 만들기
2. 원하는 권한을 응용 프로그램에 할당합니다.
3. 응용 프로그램의 사용자 자격 증명을 사용하여 보안 토큰을 얻습니다.
4. 토큰을 사용하여 API에 Microsoft 365 Defender 있습니다.

자세한 내용은 사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 **[만들기를 참조하세요.](api-create-app-user-context.md)**

## <a name="partner-context"></a>파트너 컨텍스트

여러 테넌트에서 많은 사용자에게 앱을 제공해야 하는 경우 이 [컨텍스트를 사용하세요.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. 다중 Azure Active Directory 응용 프로그램을 만들 수 있습니다.
2. 원하는 권한을 응용 프로그램에 할당합니다.
3. 각 [테넌트에서](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 앱에 대한 관리자 동의를 얻습니다.
4. 고객의 테넌트 ID에 따라 사용자 자격 증명을 사용하여 보안 토큰을 얻습니다.
5. 토큰을 사용하여 API에 Microsoft 365 Defender 있습니다.

자세한 내용은 Api에 대한 파트너 액세스로 앱 **[만들기를 Microsoft 365 Defender 참조하세요.](api-partner-access.md)**

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 Defender API 개요](api-overview.md)
- [사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Azure Key Vault를 사용하여 서버 앱의 비밀 관리](/learn/modules/manage-secrets-with-azure-key-vault/)
- [앱 API에 액세스하는 'Hello world' Microsoft 365 만들기](api-hello-world.md)
