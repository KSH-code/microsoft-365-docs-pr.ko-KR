---
title: MSSP(관리되는 보안 서비스 공급자) 액세스 제공
description: 사이트 포털에서 Microsoft Defender 보안 센터 변경 내용에 Microsoft 365 Defender 자세한 내용
keywords: Microsoft 365 Defender 포털, microsoft Defender for Office 365, Endpoint용 Microsoft Defender, MDO, MDE, 단일 창, 수렴형 포털, 보안 포털, Defender 보안 포털 시작
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 232cb81080a8d478b57b2f87a8b98752e51b0c20
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58258409"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>MSSP(관리되는 보안 서비스 공급자) 액세스 제공 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**적용 대상:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

다중 테넌트 위임 액세스 솔루션을 구현하기 위해 다음 단계를 수행합니다.

1. [Microsoft 365 Defender(Azure](/windows/security/threat-protection/microsoft-defender-atp/rbac) AD) 그룹에서 끝점에 대한 Defender에서 역할 기반 액세스 제어를 Azure Active Directory 연결합니다.

2. 액세스 [요청 및 프로비저닝을 위해](/azure/active-directory/governance/identity-governance-overview) 거버넌스 액세스 패키지를 구성합니다.

3. Microsoft Myaccess에서 액세스 요청 및 [감사를 관리합니다.](/azure/active-directory/governance/entitlement-management-request-approve)

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-defender-portal"></a>Microsoft Defender for Endpoint에서 역할 기반 액세스 제어를 Microsoft 365 Defender 포털

1. **고객 AAD에서 MSSP 리소스에 대한 액세스 그룹 만들기: 그룹**

    이러한 그룹은 포털에서 끝점용 Defender에서 만든 역할에 Microsoft 365 Defender 연결됩니다. 이렇게 하여 고객 AD 테넌트에서 세 개의 그룹을 만드면 됩니다. 이 예제에서는 다음 그룹을 생성합니다.

    - 계층 1 분석가
    - 계층 2 분석가
    - MSSP 분석가 승인자  

2. 포털 역할 및 그룹의 끝점에 대한 Customer Defender에서 적절한 액세스 수준에 Microsoft 365 Defender 끝점 역할에 대한 Defender를 만들 수 있습니다.

    고객 Microsoft 365 Defender 포털에서 RBAC를 사용하도록 설정하려면 사용 권한 > **끝점** 역할 & 그룹 > 전역 관리자 또는 보안 관리자 권한이 있는 사용자 계정을 사용하여 역할에 액세스합니다.

    ![MSSP 액세스 이미지](../../media/mssp-access.png)

    그런 다음 MSSP SOC 계층 요구 사항을 충족하는 RBAC 역할을 생성합니다. "할당된 사용자 그룹"을 통해 이러한 역할을 만든 사용자 그룹에 연결합니다.

    가능한 두 가지 역할:

    - **계층 1 분석가** <br>
      라이브 응답을 제외한 모든 작업을 수행하고 보안 설정을 관리합니다.

    - **계층 2 분석가** <br>
      실시간 응답이 추가된 계층 1 [기능](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    자세한 내용은 역할 기반 액세스 [제어 사용을 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/rbac)

## <a name="configure-governance-access-packages"></a>거버넌스 액세스 패키지 구성

1. **고객 AAD에서 MSSP를 연결된 조직으로 추가: ID 거버넌스**

    MSSP를 연결된 조직으로 추가하면 MSSP가 프로비전된 액세스를 요청하고 액세스할 수 있습니다. 

    이렇게 하려면 고객 AD 테넌트에서 ID 거버넌스: 연결된 조직에 액세스합니다. 새 조직을 추가하고 테넌트 ID 또는 도메인을 통해 MSSP 분석가 테넌트 검색 MSSP 분석가를 위한 별도의 AD 테넌트 만들기를 제안합니다.

2. **고객 AAD에서 리소스 카탈로그 만들기: ID 거버넌스**

    리소스 카탈로그는 고객 AD 테넌트에서 만든 액세스 패키지의 논리적 컬렉션입니다.

    이를 위해 고객 AD 테넌트에서 ID 거버넌스: 카탈로그에 액세스하고 새 **카탈로그를 추가합니다.** 이 예제에서는 **MSSP Accesses 를 호출합니다.**

    ![새 카탈로그의 이미지](../../media/goverance-catalog.png)

    자세한 내용은 리소스 카탈로그 [만들기를 참조하세요.](/azure/active-directory/governance/entitlement-management-catalog-create)

3. **MSSP 리소스 고객 AAD: ID 거버넌스에 대한 액세스 패키지 만들기**

    액세스 패키지는 승인 시 요청자에 부여되는 권한 및 액세스의 모음입니다. 

    이렇게 하여 고객 AD 테넌트에서 ID 거버넌스: 액세스 패키지에 액세스하고 새 **액세스 패키지를 추가합니다.** MSSP 승인자 및 각 분석가 계층에 대한 액세스 패키지를 생성합니다. 예를 들어 다음 계층 1 분석가 구성은 다음과 같은 액세스 패키지를 만듭니다.

    - AD 그룹 **MSSP** 분석가 승인자의 구성원이 새 요청을 승인해야 합니다.
    - SOC 분석가가 액세스 확장을 요청할 수 있는 연간 액세스 검토가 있습니다.
    - MSSP SOC 테넌트의 사용자만 요청할 수 있습니다.
    - 365일 후에 액세스 자동 만료

    ![새 액세스 패키지의 이미지](../../media/new-access-package.png)

    자세한 내용은 새 액세스 패키지 [만들기를 참조하세요.](/azure/active-directory/governance/entitlement-management-access-package-create)

4. **고객 AAD에서 MSSP 리소스에 대한 액세스 요청 링크 제공: ID 거버넌스**

    내 액세스 포털 링크는 MSSP SOC 분석가가 만든 액세스 패키지를 통해 액세스를 요청하는 데 사용됩니다. 링크는 지속형으로, 시간이 지날 때 새 분석가에게 동일한 링크를 사용할 수 있습니다. 분석가 요청은 MSSP 분석가 승인자 의 승인을 **위해 큐로 들어갑니다.**

    ![액세스 속성의 이미지](../../media/access-properties.png)

    링크는 각 액세스 패키지의 개요 페이지에 있습니다.

## <a name="manage-access"></a>액세스 관리

1. 고객 및/또는 MSSP 내 액세스 요청을 검토하고 권한을 부여합니다.

    액세스 요청은 MSSP 분석가 승인자 그룹의 구성원에 의해 고객 내 액세스에서 관리됩니다.

    이렇게 하는 경우 를 사용하여 고객의 myaccess에 `https://myaccess.microsoft.com/@<Customer Domain>` 액세스합니다.

    예: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. UI의 승인 섹션에서  요청을 승인하거나 거부합니다.

     이 시점에서 분석가 액세스가 프로비전되고 각 분석가가 고객의 Microsoft 365 Defender 포털에 액세스할 수 있습니다.

    `https://security.microsoft.com/?tid=<CustomerTenantId>` 할당된 사용 권한 및 역할과 함께 사용할 수 있습니다.

> [!IMPORTANT]
> Microsoft 365 Defender 포털에서 끝점용 Microsoft Defender에 대한 위임된 액세스는 현재 브라우저 창당 하나의 테넌트에 액세스할 수 있도록 허용합니다.
